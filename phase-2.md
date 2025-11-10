
***

# Phase 2: Org Setup & Configuration (To Do List App)

### Step 1: Setup Developer Org
1. Go to [https://developer.salesforce.com/signup](https://developer.salesforce.com/signup)
2. Register for a free Salesforce Developer Edition org.
3. Verify your email and log in to your new org.


### Step 2: Setup Company Profile
1. Navigation: Setup → Company Information
2. Update and review info:
   - Organization Name: (Your Company/Team Name)
   - Default Currency: e.g. INR (₹)
   - Time Zone, Fiscal Year: Set as needed
3. Business Hours
   - Path: Setup → Business Hours
   - Example: Mon–Fri, 9AM–6PM
4. Holidays
   - Example: Enter public holidays or days when no tasks should be assigned



### Step 3: Create Custom Profiles
1. Navigation: Setup → Profiles
2. Clone Standard User profile into:
   - Manager Profile – For managers who assign and monitor tasks
   - Employee Profile – For employees who receive tasks
3. Assign the right object/field permissions:
   - Manager: Full access on To Do Task
   - Employee: Read/Edit on assigned tasks only


### Step 4: Define Roles
1. Navigation: Setup → Roles → Set Up Roles → Expand All
2. Create hierarchy:
   - Manager (top level)
   - Employee (reports to Manager)
   - *(Screenshot of role hierarchy can be added here)*



### Step 5: Create Users
1. Navigation: Setup → Users → New User
2. Assign details such as:
   - License: Salesforce Platform or Salesforce 
   - Profile: Manager Profile or Employee Profile
   - Role: Manager or Employee
3. Create sample users: One Manager, One Employee

### Step 6: Org-Wide Defaults (OWD) & Sharing
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
