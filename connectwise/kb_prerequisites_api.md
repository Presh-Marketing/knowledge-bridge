# Prerequisites & API Setup

## What You Need Before Starting

Before you can connect TD SYNNEX Digital Bridge to ConnectWise PSA, you need to gather some important information and set up a few things in both systems.

### TD SYNNEX Requirements

You need a valid TD SYNNEX account to use this integration. Specifically, you must have:

- **TD SYNNEX Electronic Commerce (EC) account** - This is your regular TD SYNNEX login
- **Access to TD SYNNEX Digital Bridge** - Your account must be enabled for Digital Bridge
- **ConnectWise PSA connector enabled** - Contact TD SYNNEX support if you don't see ConnectWise PSA in your Connector Bridge

### ConnectWise PSA Requirements

In ConnectWise PSA, you need to create a special user account just for the integration. This is called an API member.

## Setting Up Your ConnectWise API User

### Step 1: Create the API Member

1. Log into ConnectWise PSA as an administrator
2. Go to **System → Members → API Members**
3. Click **New** to create a new API member
4. Fill in the basic information:
   - First Name: TD SYNNEX
   - Last Name: Integration
   - Email: (use your admin email)
   - Security Level: Choose a role with the permissions listed below

### Step 2: Set the Required Permissions

Your API member needs specific permissions to work properly. Here's exactly what permissions are required:

| Module / Function | Add | Edit | Inquire | Delete | Close | Why This is Needed |
|-------------------|:---:|:----:|:-------:|:------:|:-----:|-------------------|
| **Sales → Opportunities** | ✔ | ✔ | ✔ | | | Updates product prices and availability in quotes |
| **Procurement → Product Catalog** | ✔ | ✔ | ✔ | | | Creates and maintains TD SYNNEX products in your catalog |
| **Procurement → Purchase Orders** | ✔ | ✔ | ✔ | ✔ | ✔ | Creates purchase orders and updates their status |
| **Company → Companies/Contacts** | ✔ | ✔ | ✔ | | | Creates the TD SYNNEX vendor and reads shipping information |
| **System → Callback Entries** | ✔ | ✔ | | | | Sets up webhooks for order notifications |
| **System → Table Setup** | | ✔ | ✔ | | | Creates custom fields and purchase order status values |

**Important:** If any of these permissions are missing, the integration will fail during setup.

### Step 3: Generate API Keys

After creating the API member:

1. Open the API member's profile
2. Go to the **API Keys** tab
3. Click **Generate Key** to create a public key
4. Click **Generate Secret** to create a private key
5. **Write down these keys immediately** - you won't be able to see them again
6. Also note your **Company ID** - you'll need this too

## What Happens During Integration Setup

When you connect the integration, it will automatically create several things in your ConnectWise PSA system:

### Automatic Setup Items

1. **TD SYNNEX Vendor Company** - A new vendor company named "TD SYNNEX"

![TD SYNNEX Vendor Setup](/public/assets/images/cw-vendor-setup.png)

2. **Webhook Callbacks** - Automatic notifications when purchase orders are created or changed
3. **Custom Purchase Order Status Values**:
   - Send to TDS
   - TDS Accepted
   - TDS Released
   - TDS Shipped
   - TDS Invoiced
   - TDS Closed
4. **Custom Fields** - Additional fields for tracking TD SYNNEX order information
5. **Product Categories** - Categories based on your TD SYNNEX subscriptions

### Integration Workflow Overview

Here's how the integration works once it's set up:

The integration handles the complete order lifecycle:
- **Product Sync**: Daily updates of up to 20,000 TD SYNNEX products
- **Price Checking**: Real-time pricing when you add products to opportunities
- **Order Submission**: Automatic purchase order creation in TD SYNNEX
- **Status Updates**: Real-time tracking of order status and shipping information

## Next Steps

Once you have:
- ✅ Your TD SYNNEX EC credentials
- ✅ A ConnectWise API member with proper permissions
- ✅ Your API keys and Company ID

You're ready to proceed to [Connecting & Activating the Connector](./kb_connect_activation.md).

## Troubleshooting Common Issues

**Problem**: "Permission denied" error during setup
**Solution**: Double-check that your API member has all the required permissions listed above

**Problem**: Can't generate API keys
**Solution**: Make sure you're logged in as an administrator and the API member is saved first

**Problem**: Integration fails to connect
**Solution**: Verify your Company ID is correct and your API keys are active

