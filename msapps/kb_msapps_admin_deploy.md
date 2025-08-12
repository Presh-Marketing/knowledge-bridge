# Microsoft Apps Plugin – Admin Deployment

This guide walks administrators through deploying the TD SYNNEX Digital Bridge plugin for their organization via the Microsoft 365 Admin Center.

## Step 1: Navigate to Integrated Apps  

1. Go to **Microsoft 365 Admin Center** → **Settings** → **Integrated Apps**
2. Direct URL: `https://admin.microsoft.com/?&source=applauncher#/Settings/IntegratedApps`

![Integrated apps](/public/assets/images/msapps_step7_integrated_apps.png)

## Step 2: Get the App  

1. Once on the Integrated Apps page, click **"Get apps"** at the top of the app table
2. Search for **"TD SYNNEX Digital Bridge"**
3. Click **"Get it now"** when you find the app

![Get apps](/public/assets/images/msapps_step8_get_apps.png)

## Step 3: Deploy the App

1. Follow the on-screen steps to accept permissions
2. Grant access to the new Microsoft Plugin for TD SYNNEX Digital Bridge
3. Review the permissions carefully before approving

![Deploy config](/public/assets/images/msapps_step9_deploy_app.png)

**Permissions Overview:**
- User profile access (name, email)
- Team/chat metadata (channel names, rosters)
- User-initiated message content access
- Secure API calls to TD SYNNEX services

## Step 4: Assign Users

Determine access levels for your organization:

### Deployment Options:
* **Entire Organization** – All users can access the plugin
* **Specific Groups** – Only designated groups have access
* **Specific Users** – Individual user access

![Add users](/public/assets/images/msapps_step10_add_users.png)

**Important Notes:**
- Any user with access will still need to enter their TD SYNNEX EC Express credentials to log in
- The plugin will appear in both Outlook and Teams once deployed
- Users can pin the app for quick access in their sidebar

## Post-Deployment

After successful deployment:
1. **Notify users** that the plugin is available
2. **Share user installation guide** for individual setup steps
3. **Provide TD SYNNEX login credentials** information
4. **Monitor usage** through Microsoft 365 Admin Center analytics

The plugin will now be available to your specified users across Outlook and Teams platforms.