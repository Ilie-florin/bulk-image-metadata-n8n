# 📁 Automated File Upload & Processing Workflow (n8n)

This workflow monitors a Google Drive folder for new files, sends them to an external processing API, stores the processed output in another Drive folder, writes metadata to Google Sheets, and deletes the original file. It uses environment variables for flexible configuration and security.

---

## 🚀 Features

- Detects new files in a Google Drive folder
- Sends the file to an external processing API
- Downloads the processed result
- Uploads the processed result to another Google Drive folder
- Extracts and stores metadata (title, description, tags) to a Google Sheet
- Deletes the original file after processing

---

## 🔐 Environment Variables

Before using this workflow, you need to set up the following environment variables in n8n:

| Variable Name              | Description                                  |
|---------------------------|----------------------------------------------|
| `API_KEY`                 | API Key to authenticate with external API    |
| `API_UPLOAD_URL`          | API endpoint URL for file processing         |
| `API_USER`                | Identifier used in the API upload request    |
| `GDRIVE_CREDENTIAL_NAME`  | Name of Google Drive credential in n8n       |
| `GDRIVE_WATCH_FOLDER_ID`  | ID of the Drive folder to monitor            |
| `GDRIVE_UPLOAD_FOLDER_ID` | ID of the Drive folder to store processed files |
| `SHEETS_CREDENTIAL_NAME`  | Name of Google Sheets credential in n8n      |
| `SHEET_ID`                | Google Sheets ID to log metadata             |

---

## 🧾 Obtaining Your API Key

To use the external image-processing API, you must register and generate an API key:

1. Visit [http://image-stock-desk.ns5.club](http://image-stock-desk.ns5.club)
2. Create an account or log in
3. Navigate to your profile or developer settings
4. Generate your **API Key**
5. Save the key securely and assign it to the `API_KEY` variable

---

## 📦 Deployment Instructions

### 🖥️ Self-Hosted (Using `.env`)
1. Copy `.env.template` to `.env`
2. Add your actual values to `.env`
3. Start n8n with environment variable support:
   ```bash
   docker run -it --env-file .env -p 5678:5678 n8nio/n8n
