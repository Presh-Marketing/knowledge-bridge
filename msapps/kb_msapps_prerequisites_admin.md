# TD SYNNEX Digital Bridge – Microsoft Apps Plugin  
## Prerequisites & Admin Approval

![AppSource listing](/public/assets/images/msapps_step1_appsource.png)

## Overview

The **TD SYNNEX Digital Bridge Microsoft Apps Plugin** brings powerful TD SYNNEX data directly into Microsoft Teams and Outlook, enabling seamless access to pricing, stock, orders, and more without leaving your Microsoft workspace.

### Key Features

* **Live Data Integration** – Stream pricing, inventory, order tracking, subscriptions, and My Business Dashboard straight into Outlook and Teams
* **Single Sign-On** – One install, one sign-on—no more jumping to EC Express
* **Cross-Platform** – Works in Outlook, Teams (desktop, web, mobile)
* **Unified Experience** – Quote faster, resolve order questions, and reach TD SYNNEX contacts without leaving your inbox or chat

## How the Plugin Shows Up

| Surface | What Users See | Why It Matters |
|---------|---------------|----------------|
| **Personal App** (Outlook sidebar & Teams left rail) | Full panel with Part Search, Order Status, My Business Dashboard, Subscriptions, and Contacts | One click to all critical data—follows the user across Outlook, Teams (desktop, web, mobile) |
| **Tabs** (Teams channels, chats, meetings) | Pin any plugin view (e.g., live order board) at the top of a workspace | Keeps project stakeholders aligned without extra logins |

*Note: The plugin does not post proactive messages today; message-extension support is on the roadmap.*

## Permissions Requested at Install

The unified manifest requires the least-privilege Graph scopes needed to operate in both Outlook and Teams:

* **User profile** – Read basic info (name, email) to personalize the panel
* **Team / chat metadata** – Read channel or chat name and roster so the plugin can load participant-specific pricing or contacts
* **Message content (user initiated)** – Access text the user selects (e.g., PO # or Part #) to run a search; no background mailbox access
* **Send and receive data to TD SYNNEX APIs** – Secure outbound HTTPS calls for pricing, inventory, order status, and dashboard metrics

**Important:** The plugin is multi-tenant; once an admin grants consent in either Teams Admin Center or Microsoft 365 › Integrated Apps, Outlook and Teams are both covered. No separate Outlook approval is required.

## Eligibility Requirements

### User Permissions
* Users must have the necessary permissions to install apps within Microsoft Teams
* If organizational policies restrict app installations, only users with admin permissions or those in roles with the ability to install apps can add the plugin

### Team and Chat Settings
* The app can be added to group chats, channels, or meetings as a tab at the top
* The organization's Microsoft Teams admin center must allow third-party apps or this specific plugin to be installed

### Personal Access
* Any individual user with standard permissions in Teams can add the plugin as a personal app
* Admin must not have restricted this feature

### Profile Information Requirements
Users must be willing to grant access to their profile information, including:
* Name, email address, company name, and preferred language
* Users within the organization must use Teams with fully configured profiles to allow integration

## Admin Prerequisites

Before deployment, ensure:
* **Microsoft 365 Admin Center** access
* **Teams Admin Center** permissions  
* Authority to approve third-party apps for your organization
* Understanding of your organization's app deployment policies