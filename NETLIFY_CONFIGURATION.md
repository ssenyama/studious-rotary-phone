# Netlify Configuration Guide for `ssenyama/studious-rotary-phone`

This guide provides a comprehensive overview of how to set up the Netlify configuration for the project `studious-rotary-phone`. It covers automatic deployment, setting up environment variables for Google Sheets API integration, build configuration, and real-time sync initialization instructions for the Sightly View Bar POS system.  

## 1. Automatic Deployment Setup

To set up automatic deployment on Netlify, follow these steps:

1. **Connect to Your GitHub Repository**:  
   - Go to your Netlify dashboard, and click on **New site from Git**.  
   - Choose **GitHub** as your provider and authenticate your GitHub account.  
   - Select the repository `ssenyama/studious-rotary-phone`.

2. **Configure Build Settings**:  
   - Specify the **branch to deploy** (usually `main`), and set the **build command**:
     ```bash
     npm run build
     ```
   - Set the **publish directory** to `dist` or wherever your static files are located.

3. **Automatic Deploys**:  
   - Enable **automatic deploys** to ensure that every time you push changes to your specified branch, Netlify rebuilds and deploys your site automatically.

## 2. Environment Variables for Google Sheets API Integration

To integrate Google Sheets API, you need to set environment variables in your Netlify project settings:

1. **Navigate to your Netlify dashboard**.  
2. Click on **Site settings** and then **Build & deploy**.  
3. Under **Environment**, select **Environment variables**.  
4. Add the following variables:
   - `GOOGLE_SHEETS_API_KEY`: Your Google Sheets API key.
   - `GOOGLE_SHEET_ID`: The ID of your Google Sheet.
   - `GOOGLE_SHEET_RANGE`: The range of cells you want to access, e.g., `Sheet1!A1:D10`.

## 3. Build Configuration

Ensure your build configuration is optimized for deployment on Netlify. A sample `netlify.toml` configuration file should look like this:

```toml
[build]
  command = "npm install && npm run build"
  publish = "dist"

[context.production.environment]
  NODE_ENV = "production"

[functions]
  directory = "netlify/functions"
```

1. **Create a `netlify.toml` file** if it doesn't exist in your repository root.
2. Configure the file according to your build and function needs.

## 4. Real-Time Sync Initialization for Sightly View Bar POS System

To set up real-time sync for the Sightly View Bar POS system:  
1. **Set Up Webhooks** in Netlify for GitHub events: Go to **Site settings** > **Build & deploy** > **Build hooks**:
   - Create a new build hook and name it (e.g., `POS Sync`).  
   - Copy the generated URL to use in your POS system.

2. **Configure the POS System** to call this webhook URL upon relevant data changes or during initialization to ensure data sync is accurate.  

3. **Testing the Integration**:  
   - After configuring, test by making changes in your POS system, then triggering the webhook to verify data sync.

## Conclusion
This guide outlines the steps to configure your Netlify environment for the `studious-rotary-phone` project. By following these instructions, you will achieve seamless deployment and integration with the Sightly View Bar POS system. For further customization, refer to the official Netlify and Google Sheets API documentation.  

---

### Last Updated: 2026-04-08 12:21:47 UTC  
### Author: ssenyama