# Email Automation using n8n

This project demonstrates an **email automation workflow built using n8n**.  
The workflow fetches data from Google Sheets, processes email templates, and sends automated emails using Gmail.

# Overview

The workflow performs the following steps:
1. Manually triggers the workflow in n8n.
2. Reads recipient data from a Google Sheet.
3. Filters out setup/test rows.
4. Loops through the recipient list.
5. Fetches email templates from another Google Sheet.
6. Randomly selects an email template (subject & body).
7. Formats the email body into HTML.
8. Sends an automated email using Gmail.

# Tools & Technologies Used

- **n8n** – Workflow automation
- **Google Sheets** – Data source for recipients and email templates
- **Gmail API** – Sending automated emails
- **JavaScript (n8n Code node)** – Template selection and formatting

# How to Use the Workflow

### Step 1: Open n8n
- Log in to your **n8n** instance (local or cloud).
- Navigate to the **Workflows** section.

### Step 2: Import the Workflow
1. Click **Import workflow**
2. Upload the file: Mail automation (1).json
3. The workflow will load with all nodes connected.

### Step 3: Prepare Google Sheets

This workflow uses **two Google Sheets**.
#### Sheet 1 – Recipient Data
- Must include a column named `NAME`
- Rows with `NAME = SETUP` are ignored
- Other rows are processed for automation
#### Sheet 2 – Email Templates
- Required columns:
- `Subject`
- `Body`
- One template is randomly selected per execution

### Step 4: Configure Credentials
Configure the following credentials in n8n:

- **Google Sheets OAuth2** – to read spreadsheet data
- **Gmail OAuth2** – to send automated emails

Steps:
1. Open any Google Sheets or Gmail node
2. Click **Create new credential**
3. Authenticate with your Google account
4. Save the credential

### Step 5: Execute the Workflow
- Click **Execute workflow**
- The workflow will:
1. Fetch data from Google Sheets
2. Select a random email template
3. Format the email body
4. Send the email using Gmail

### Step 6: Verify Results
- Check the **Execution Log** in n8n
- Confirm the email is received successfully

### Output
- Email is sent automatically
- Subject and body are dynamically generated
- No manual email drafting required




