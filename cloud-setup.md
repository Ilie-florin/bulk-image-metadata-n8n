# 🌐 Workflow Setup Guide for n8n Cloud

This workflow uses environment variables to keep configuration flexible and secure. Follow these steps to set up in n8n Cloud:

---

## ⚙️ Step 1: Create Environment Variables

Go to `Settings → Variables` and add the following:

| Variable Name              | Example Value                        |
|---------------------------|--------------------------------------|
| API_KEY                   | your_api_key_here                    |
| API_UPLOAD_URL            | https://api.ns5.club/api/upload    |
| API_USER                  | your_api_user                        |
| GDRIVE_CREDENTIAL_NAME    | GoogleDriveCredential                |
| GDRIVE_WATCH_FOLDER_ID    | Drive folder ID to watch             |
| GDRIVE_UPLOAD_FOLDER_ID   | Drive folder ID to save processed files |
| SHEETS_CREDENTIAL_NAME    | GoogleSheetsCredential               |
| SHEET_ID                  | Google Sheets ID                     |

---

## 🔑 Step 2: Add OAuth2 Credentials

- Navigate to `Credentials → Create Credential`
- Choose **Google Drive OAuth2** and **Google Sheets OAuth2**
- Use credential names that match the values above

---

## 🚀 Step 3: Import and Run the Workflow

- Import the cleaned JSON workflow into your n8n editor
- Trigger with a test file in the monitored Drive folder

> If you face issues accessing environment variables, verify they've been saved properly and reload the workflow.

---
