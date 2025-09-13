# Google Docs to Sheets Automation - Setup Guide

## Overview
This n8n workflow automatically reads content from 8 Google Documents and updates corresponding rows in a Google Sheets spreadsheet. It handles both text fields and dropdown selections.

## Files
- `google-docs-to-sheets-workflow.json` - The main workflow file to import into n8n

## Prerequisites
1. n8n installation (**Version 1.110.1** - tested and validated)
2. Google account with access to Google Drive, Docs, and Sheets
3. OAuth2 credentials configured for Google services

> **Note**: This workflow is specifically designed and tested for n8n Version 1.110.1. While it may work with other versions, compatibility is guaranteed only for v1.110.1.

## Setup Instructions

### 1. Import the Workflow
1. Open your n8n instance
2. Go to Workflows → Import from File
3. Select `google-docs-to-sheets-workflow.json`
4. Click Import

### 2. Configure Google Credentials

#### For Google Docs:
1. Create Google OAuth2 credentials in n8n
2. Update the "Get Google Doc" node with your credential ID
3. Replace `YOUR_GOOGLE_CREDENTIALS_ID` with your actual credential ID

#### For Google Sheets:
1. Create Google Sheets OAuth2 credentials in n8n  
2. Update the "Update Google Sheet" node with your credential ID
3. Replace `YOUR_GOOGLE_SHEETS_CREDENTIALS_ID` with your actual credential ID

### 3. Configure Document URLs
1. Open the "Setup Document URLs" code node
2. Replace the placeholder URLs with your actual Google Doc URLs:
   ```javascript
   const docUrls = [
     'https://docs.google.com/document/d/YOUR_ACTUAL_DOC_ID_1/edit',
     'https://docs.google.com/document/d/YOUR_ACTUAL_DOC_ID_2/edit',
     // ... add all 8 document URLs
   ];
   ```

### 4. Customize Data Extraction
1. Open the "Extract and Map Data" code node
2. Modify the parsing logic based on your document structure:
   - Update field extraction patterns
   - Adjust dropdown value mappings
   - Modify column assignments in `sheetValues`

### 5. Configure Spreadsheet Details
The workflow is pre-configured for your spreadsheet:
- **Spreadsheet ID**: `1nBTGgVqeQVoky9rPvZNVhmYa1XwoBjk0-GvpcB0o_1U`
- **Sheet ID**: `gid=1266026957`

If you need to change these:
1. Open the "Update Google Sheet" node
2. Update the `documentId` and `sheetName` values

## Workflow Architecture

### Node Flow:
1. **Manual Trigger** - Start the workflow manually
2. **Setup Document URLs** - Define the 8 Google Doc URLs to process
3. **Split In Batches** - Process documents one at a time
4. **Get Google Doc** - Retrieve document content from Google Docs API
5. **Extract and Map Data** - Parse content and map to spreadsheet columns
6. **Update Google Sheet** - Write/update the corresponding row
7. **Log Success** - Log completion and loop back for next document

### Key Features:
- **Sequential Processing**: Documents are processed one at a time to avoid API rate limits
- **Dropdown Support**: Automatically maps text values to valid dropdown options
- **Error Handling**: Includes basic error handling and logging
- **Flexible Mapping**: Easy to customize field extraction and column mapping

## Customization

### Document Structure
The workflow assumes documents contain structured data with patterns like:
```
Title: Document Name
Summary: Brief description
Category: Project
Status: In Progress
Priority: High
Notes: Additional comments
```

### Spreadsheet Columns
Default column mapping:
- **Column A**: Document Title
- **Column B**: Summary
- **Column C**: Category (dropdown)
- **Column D**: Status (dropdown)  
- **Column E**: Priority (dropdown)
- **Column F**: Notes
- **Column G**: Last Updated
- **Column H**: Source Document URL

### Dropdown Values
The workflow includes mapping for common dropdown values:
- **Status**: Complete, In Progress, Pending, Not Started
- **Priority**: High, Medium, Low
- **Category**: Project, Task, Issue, Feature, General

Modify these in the `mapDropdownValue` function.

## Testing
1. Ensure all credentials are properly configured
2. Test with one document first by modifying the `docUrls` array
3. Check the workflow execution log for any errors
4. Verify data appears correctly in your spreadsheet

## Troubleshooting

### Common Issues:
1. **Authentication Errors**: Verify OAuth2 credentials are set up correctly
2. **Document Access**: Ensure the service account or OAuth user has access to all documents
3. **Sheet Permissions**: Verify write permissions to the target spreadsheet
4. **API Limits**: The workflow processes documents sequentially to respect API limits

### Debugging:
- Check n8n execution logs for detailed error messages
- Use the workflow's built-in logging in the "Log Success" node
- Test individual nodes to isolate issues

## Support
If you encounter issues:
1. Check the n8n documentation for Google integrations
2. Verify your Google API quotas and permissions
3. Review the workflow execution logs for error details