# Connecting & Activating the Connector

## Overview

After you've prepared your credentials and API member (see [Prerequisites & API Setup](./kb_prerequisites_api.md)), the next step is to connect and activate the TD SYNNEX connector in the Connector Bridge portal.

This process has three main steps:
1. **Connect** - Link your TD SYNNEX and ConnectWise accounts
2. **Activate** - Let the system set up everything automatically
3. **Configure Templates** - Choose which features you want to use

## Step 1: Connecting Your Accounts

### Access Connector Bridge

1. Log into your TD SYNNEX Digital Bridge portal
2. Navigate to **Connector Bridge**
3. Find the **ConnectWise PSA** connector card
4. Click the **Connect** button

### Enter Your Connection Information

You'll see a connection form that asks for several pieces of information. Here's what to enter:

**TD SYNNEX Information:**
- **Username**: Your TD SYNNEX EC username
- **Password**: Your TD SYNNEX EC password

**ConnectWise Information:**
- **Domain**: Your ConnectWise domain (like "yourcompany.connectwiseapps.com")
- **Company ID**: The Company ID from your ConnectWise system
- **Public Key**: The public key you generated for your API member
- **Private Key**: The private key you generated for your API member

### Connection Validation

When you click **Connect**, the system will:
- Test your TD SYNNEX credentials
- Verify your ConnectWise API connection
- Check that your API member has all required permissions
- Confirm that both systems can communicate

If there are any problems, you'll see a specific error message explaining what needs to be fixed.

## Step 2: Automatic Activation

Once the connection succeeds, the integration automatically enters an **activation** phase. This is where the magic happens - the system sets up everything you need in ConnectWise PSA without you having to do it manually.

### What Gets Created Automatically

During activation, the integration creates:

**Company Setup:**
- A new vendor company named "TD SYNNEX"
- Proper vendor configuration for purchase orders

**Custom Fields:**
- "Send to TDS" field on purchase orders
- "TDS Sync Price" field on opportunities
- Additional tracking fields for order information

**Purchase Order Status Values:**
- Send to TDS
- TDS Accepted
- TDS Released
- TDS Shipped
- TDS Invoiced
- TDS Closed

**Webhook Configuration:**
- Automatic callbacks for purchase order events
- Real-time notifications when orders are created or changed

**Product Categories:**
- Categories based on your TD SYNNEX product subscriptions
- Subcategories for better organization

### Monitoring Activation Progress

You can watch the activation process in the **Sync Activity Log**. This shows:
- Which setup tasks have completed
- Any errors that need attention
- The number of records being processed

The activation is complete when all setup tasks show as successful.

## Step 3: Template Selection

After activation, you need to decide which integration templates to enable. Each template handles a specific part of the workflow:

### Available Templates

**Product Sync**
- Syncs up to 20,000 TD SYNNEX products into your ConnectWise catalog
- Runs daily to keep pricing and availability current
- Essential for using other templates

**Get Product Price & Availability**
- Provides real-time pricing when you add products to opportunities
- Updates automatically when you modify quotes
- No additional configuration needed

**Create Orders from ConnectWise**
- Automatically submits purchase orders to TD SYNNEX
- Runs every 30 minutes to check for new orders
- Updates ConnectWise with TD SYNNEX order numbers and tracking

**Get Order Status**
- Monitors TD SYNNEX orders for status changes
- Updates purchase orders with shipping information
- Requires the "Send to TDS" field to be set to true

### Enabling Templates

To enable a template:
1. Go to the **Integration Templates** tab
2. Find the template you want to use
3. Toggle the switch to **Active**
4. The template will start working immediately

## Verification and Testing

### Check Your Setup

After activation, verify everything is working:

1. **Check the TD SYNNEX vendor** - Go to Company → Companies and look for "TD SYNNEX"
2. **Verify custom fields** - Create a test purchase order and look for the new fields
3. **Test product sync** - Enable the Product Sync template and check your product catalog
4. **Review webhooks** - Go to System → Callback Entries to see the new callbacks

### Test the Integration

To test that everything is working:

1. **Create a test opportunity** with TD SYNNEX products
2. **Set the "TDS Sync Price" field** to "Get TDS Price"
3. **Wait a few minutes** for the price update
4. **Check that prices updated** in the opportunity

## Common Issues and Solutions

### Connection Problems

**Error: "Invalid API credentials"**
- Double-check your public and private keys
- Verify your Company ID is correct
- Make sure your API member is active

**Error: "Permission denied"**
- Review the permissions matrix in the Prerequisites article
- Ensure your API member has all required permissions
- Check that the security level includes the necessary modules

### Activation Problems

**Error: "Failed to create custom fields"**
- Verify your API member has System → Table Setup permissions
- Check that you're not hitting ConnectWise field limits
- Contact support if the issue persists

**Error: "Webhook creation failed"**
- Ensure System → Callback Entries permissions are set
- Check that your ConnectWise system allows external callbacks
- Verify your firewall isn't blocking the webhook URLs

## Next Steps

With the connector successfully connected and activated, you're ready to:

1. **Configure your templates** - See [Integration Templates](./kb_templates.md) for detailed setup
2. **Start syncing products** - Enable Product Sync to populate your catalog
3. **Test the workflow** - Create a test opportunity and purchase order

The integration is now ready to streamline your TD SYNNEX ordering process!

