
# Phase 3: Data Modeling & Relationships (To Do List App)

### Step 1: Create Custom Object
<img width="1280" height="703" alt="Screenshot 2025-11-10 at 12 35 22 PM" src="https://github.com/user-attachments/assets/d339d1e0-4bec-4f85-88ea-949e31f92e0d" />

1. Go to Salesforce Setup.
2. Click on **Object Manager**.
3. Click **Create** > **Custom Object**.
4. Enter:
   - Label: "ToDo Task"
   - Plural Label: "ToDo Tasks"
   - Object Name: "ToDo_Task"
   - Record Name: Task Name (Text)
   - Select "Launch New Custom Tab Wizard after saving" for easy navigation
   - Click **Save**

### Step 2: Add Fields to Custom Object
<img width="1280" height="703" alt="Screenshot 2025-11-10 at 12 37 45 PM" src="https://github.com/user-attachments/assets/cc9a6205-4c91-41e8-a2e7-063f67907f1a" />

1. In "Fields & Relationships" section of "ToDo Task" object, click **New**.
2. Add key fields:
   - Description (Long Text Area)
   - Due Date (Date)
   - Status (Picklist: Not Started, In Progress, Completed)
   - Priority (Picklist: Low, Medium, High)
   - Comments (Long Text Area)

***

### Step 3: Lookup Relationship from Task to User
1. In "Fields & Relationships", click **New**.
2. Select **Lookup Relationship**.
3. Related To: **User**.
4. Field Label: "Assigned To"
5. Field Name: "Assigned_To"
6. Add this field to all page layouts as needed
7. Click **Save**


### Step 4: Page Layouts
<img width="1280" height="703" alt="Screenshot 2025-11-10 at 12 38 48 PM" src="https://github.com/user-attachments/assets/f51378f1-2a14-4bdc-b2ae-7ab6d5ef41a7" />

1. Go to "Page Layouts" for "ToDo Task" object
2. Create/edit layouts:
   - Employee: Can edit only Status and Comments
   - Manager: Can edit all fields, assign tasks


### Step 5: Schema Builder – Visualize Relationships
1. Go to Salesforce Setup
2. Search for "Schema Builder" and open it
3. In left panel, select "ToDo Task" and "User"
4. Visualize that "ToDo Task" has a lookup pointing to User ("Assigned To" relationship)
5. Drag, arrange, and save diagram as needed



### Step 6: Compact Layouts
1. Click on "Compact Layouts" in "ToDo Task" object
2. Set default compact layout to show: Task Name, Status, Due Date, Priority
