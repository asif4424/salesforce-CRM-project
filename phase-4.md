# Phase 4: Process Automation (Admin) (To Do List App)

### Step 1: Create Validation Rules

**A. Restrict Employees to Only Edit Assigned Tasks**
   1. Go to Salesforce Setup → Object Manager → ToDo Task → Validation Rules.
   2. Click "New".
   3. Formula:  
      ```
      AND(
        $Profile.Name = "Employee Profile",
        Assigned_To__c <> $User.Id
      )
      ```
   4. Error Message: "You can only edit tasks assigned to you."
   5. Save.

**B. Due Date Must Be in the Future**
   1. Go to Validation Rules for ToDo Task.
   2. Click "New".
   3. Formula:  
      ```
      Due_Date__c < TODAY()
      ```
   4. Error Message: "Due Date must be today or a future date."
   5. Save.


### Step 2: Setup Email Alerts

**A. Task Assignment Email**
   1. Create a Lightning Email Template: "Task Assignment Notification".
   2. Go to Setup → Email Alerts.
   3. New Alert: When ToDo Task is assigned, send email to Assigned_To__c.

**B. Overdue Task Email**
   1. Create a Lightning Email Template: "Overdue Task Alert".
   2. Scheduled Flow triggers email if Due Date < TODAY() and Status ≠ "Completed".

**C. Task Completion Email**
   1. Create a Lightning Email Template: "Task Completion Notification".
   2. Configure Flow to trigger email to Manager when Status = "Completed".


### Step 3: Build Flows & Automations

**A. Task Assignment Flow**  
   1. Go to Setup → Flow → New Flow (Record-Triggered).
   2. Object: ToDo Task, Trigger: On Create.
   3. Action: Send "Task Assignment" email to Assigned User.

**B. Task Completion Flow**  
   1. New Flow: Trigger on Status update to "Completed".
   2. Action: Send "Task Completion" email to Manager.

**C. Overdue Task Scheduled Flow**  
   1. Scheduled Flow: Runs daily.
   2. Queries ToDo Task records that are overdue and incomplete.
   3. Action: Send "Overdue Task" emails.


### Step 4: Field Updates

**A. Automatic Status Set**
   1. Record-Triggered Flow: On Create, if Status field is blank, set Status to "Not Started".

**B. Overdue Flag**
   1. Add custom checkbox field "Overdue__c" to ToDo Task.
   2. Scheduled Flow: If task is overdue, set Overdue__c = TRUE.
