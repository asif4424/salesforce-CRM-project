# Phase 7: Integration & External Access (To Do List App)

### Step 1: Email Integration

1. Configure Salesforce email settings to enable system email notifications for task assignment, completion, and overdue alerts.
2. Set up organization-wide email addresses if you want emails sent from a branded address.

### Step 2: Mobile Access

1. Test your TaskMaster app and Lightning pages on Salesforce mobile app (Android or iOS).
2. Make sure all custom components and pages are mobile-compatible.
3. Adjust layouts/components in Lightning App Builder for better mobile usability if needed.

### Step 3: External API Integrations (Optional)

1. If you need to connect to external systems (Google Calendar, Slack, or another HR app), set up Named Credentials in Salesforce Setup.
2. Create or configure Apex classes/integrations for external REST or SOAP calls.
3. Example use case: When a task is assigned, push an event/reminder to a Google Calendar for the employee.


### Step 4: Experience Cloud (Optional)

1. If you want employees to access the To Do List from an external portal, set up an Experience Cloud site.
2. Expose necessary objects, fields, and Lightning components on the portal page.

### Step 5: Security Review

1. Double-check user access, sharing rules, and field-level security, especially if exposing functionality externally.
2. Set up IP restrictions or login hours for sensitive users if required.

### Step 6: Test Integrations

1. Create sample records or use Swagger/Postman to test external API connections.
2. Validate that emails, mobile features, and portals work as expected.
3. Document any issues and resolutions.
