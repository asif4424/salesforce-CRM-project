
# Phase 5: Apex Programming (Developer) (To Do List App)



### Step 1: Set Up Apex Triggers

**A. Default Status Trigger (Task Creation)**
   1. Create a trigger on the ToDo Task object (before insert).
   2. Logic: If Status is empty on creation, set it to "Not Started".
   3. Example:
      ```
      trigger ToDoTaskDefault on ToDo_Task__c (before insert) {
          for (ToDo_Task__c t : Trigger.new) {
              if (t.Status__c == null) {
                  t.Status__c = 'Not Started';
              }
          }
      }
      ```

**B. Completion Trigger (Task Done)**
   1. Create an after update trigger on ToDo Task.
   2. Logic: When Status changes to "Completed", update related fields or send reporting.
   3. Example:
      ```
      trigger ToDoTaskCompletion on ToDo_Task__c (after update) {
          for (ToDo_Task__c t : Trigger.new) {
              ToDo_Task__c old = Trigger.oldMap.get(t.Id);
              if (t.Status__c == 'Completed' && old.Status__c != 'Completed') {
                  // Business logic here (e.g., log completion)
              }
          }
      }
      ```


### Step 2: Create Apex Classes

**A. TaskService**
   - Utility class for bulk assignment or common logic.
   - Example:
     ```
     public class TaskService {
         public static void assignTasks(List<ToDo_Task__c> tasks, Id managerId) {
             for (ToDo_Task__c t : tasks) {
                 t.OwnerId = managerId;
             }
             update tasks;
         }
     }
     ```

**B. NotificationService (Optional)**
   - Send custom notifications or emails if declarative automation is not enough.


### Step 3: Write SOQL Queries

**A. Overdue Tasks**
   ```
   List<ToDo_Task__c> overdueTasks = [
      SELECT Id, Name, Assigned_To__r.Email
      FROM ToDo_Task__c
      WHERE Due_Date__c < :Date.today() AND Status__c != 'Completed'
   ];
   ```

**B. Task Reporting**
   ```
   AggregateResult[] results = [
      SELECT Assigned_To__c, COUNT(Id) cnt
      FROM ToDo_Task__c
      WHERE Status__c = 'Completed'
      GROUP BY Assigned_To__c
   ];
   ```


### Step 4: Test Classes

1. For each trigger and class, create @IsTest methods to ensure at least 75% code coverage.
2. Example:
   ```
   @IsTest
   static void testDefaultStatusTrigger() {
       ToDo_Task__c t = new ToDo_Task__c(Name='Test', Assigned_To__c=UserInfo.getUserId(), Due_Date__c=Date.today().addDays(1));
       insert t;
       t = [SELECT Status__c FROM ToDo_Task__c WHERE Id=:t.Id];
       System.assertEquals('Not Started', t.Status__c);
   }
   ```

### Step 5: Batch Apex (Optional)

**A. BatchOverdueNotifier**
   - Class implementing Database.Batchable<ToDo_Task__c>.
   - Queries overdue tasks and sends reminder emails in bulk.
   - Scheduled via Apex Scheduler.
