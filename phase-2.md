
***

# Phase 2: Org Setup & Configuration (To Do List App)

### Step 1: Setup Developer Org
1. Go to [https://developer.salesforce.com/signup](https://developer.salesforce.com/signup)
2. Register for a free Salesforce Developer Edition org.
3. Verify your email and log in to your new org.
<img width="1171" height="614" alt="Screenshot 2025-11-10 at 11 30 52 AM" src="https://github.com/user-attachments/assets/65042696-11ef-4547-99eb-e9fc44de6e4e" />


### Step 2: Setup Company Profile

<img width="1280" height="704" alt="Screenshot 2025-11-10 at 11 35 34 AM" src="https://github.com/user-attachments/assets/5aee477f-0697-4fd0-9541-cf97f0a1ad89" />

1. Navigation: Setup → Company Information
2. Update and review info:
   - Organization Name: (Your Company/Team Name)
   - Default Currency: e.g. INR (₹)
   - Time Zone, Fiscal Year: Set as needed
  
<img width="1280" height="704" alt="Screenshot 2025-11-10 at 11 38 05 AM" src="https://github.com/user-attachments/assets/353acacc-7d9a-4aa4-b787-c0f9f71ac078" />

3. Business Hours
   - Path: Setup → Business Hours
   - Example: Mon–Fri, 9AM–6PM
4. Holidays
   - Example: Enter public holidays or days when no tasks should be assigned



### Step 3: Create Custom Profiles


1. Navigation: Setup → Profiles
2. Clone Standard User profile into:
   - Manager Profile – For managers who assign and monitor tasks
   <img width="1280" height="716" alt="Screenshot 2025-11-10 at 11 41 13 AM" src="https://github.com/user-attachments/assets/2c48f7ea-3492-4385-b401-5c6e6e26dd39" />

   - Employee Profile – For employees who receive tasks
     <img width="1280" height="716" alt="Screenshot 2025-11-10 at 11 41 34 AM" src="https://github.com/user-attachments/assets/00133fe5-b9db-433b-b184-9a872c1453e1" />

3. Assign the right object/field permissions:
   - Manager: Full access on To Do Task
   - Employee: Read/Edit on assigned tasks only


### Step 4: Define Roles
1. Navigation: Setup → Roles → Set Up Roles → Expand All
2. Create hierarchy:
   - Manager (top level)
   - Employee (reports to Manager)
   <img width="699" height="385" alt="Screenshot 2025-11-10 at 11 44 16 AM" src="https://github.com/user-attachments/assets/5f1a8bd8-e57a-4669-b755-493e51126e7e" />




### Step 5: Create Users
<img width="1280" height="703" alt="Screenshot 2025-11-10 at 11 45 43 AM" src="https://github.com/user-attachments/assets/b6f5afaf-f890-49cf-bf71-e85ad7c4a16c" />

1. Navigation: Setup → Users → New User
2. Assign details such as:
   - License: Salesforce Platform or Salesforce 
   - Profile: Manager Profile or Employee Profile
   - Role: Manager or Employee
3. Create sample users: One Manager, One Employee

### Step 6: Org-Wide Defaults (OWD) & Sharing
<img width="1280" height="703" alt="Screenshot 2025-11-10 at 11 47 02 AM" src="https://github.com/user-attachments/assets/e7269b76-4f9d-4052-82d9-5d96ae470c52" />

1. Navigation: Setup → Sharing Settings
2. Set OWD:
   - ToDo Task Object = Private (Only owner/manager can view)
   - Any other related Object = Public Read Only as applicable
3. Sharing Rules:
   - Manager should be able to see all tasks for the team
   - Employees see only their own assigned tasks

### Results & Outcomes
- Organization branding set, business hours configured
- Clear Manager–Employee role hierarchy in place
- Secure sharing model (tasks private by default)
- Profiles tailored for robust permission control
