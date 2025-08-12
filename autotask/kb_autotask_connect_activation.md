# Connecting & Activating the Connector

## Getting Started with the Connection

Now that you have your Autotask API credentials ready, it's time to connect TD SYNNEX Digital Bridge to your Autotask PSA system. This process establishes a secure connection between the two systems so they can share information automatically.

### What You Need

Before starting the connection process, make sure you have:

- ✅ **API Username** - The username generated for your Autotask API-only user
- ✅ **API Secret** - The password/secret generated for your API user
- ✅ **Tracking Identifier** - The ApiIntegrationCode assigned to your API user
- ✅ **Email Address** - The email associated with your Autotask administrator or API user
- ✅ **Active Autotask Account** - Your API user must be active and have proper permissions

### Important Email Requirement

The email address you use during connection must correspond to an active resource in your Autotask system. This is typically the same email you used when creating the API user. TD SYNNEX uses this email to associate orders and activities with your account.

## Step 1: Access the Autotask Connector

### Navigate to Connector Bridge

1. **Log into TD SYNNEX Digital Bridge**
   - Use your regular TD SYNNEX Electronic Commerce credentials
   - Go to the main Digital Bridge portal

2. **Open Connector Bridge**
   - Click **Connector Bridge** in the top navigation bar
   - Select **Manage Connectors** from the dropdown menu

3. **Find the Autotask Connector**
   - Look for **Autotask** in the list of available connectors
   - If this is your first setup, the status will show "Not Connected"
   - Click on the Autotask connector to open it

### Understanding Connector Status

**Not Connected**: The connector has never been set up or was disconnected.

**Connected**: The connector is active and working properly.

**Error**: There's an issue with the connection that needs attention.

**Disabled**: The connector is temporarily turned off.

## Step 2: Enter Your Autotask Credentials

### Start the Connection Process

1. **Click Connect**
   - If this is your first time, click the **Connect** button
   - If you're reconnecting, click **Reconnect**
   - This opens the credential entry form

2. **Complete the Authorization Form**
   - A form will appear requesting your Autotask API information
   - Fill out each field carefully and completely

### Credential Form Fields

**Email Address**:
- Enter the email address of your Autotask administrator
- This must match an active resource in your Autotask system
- Usually the same email used when creating the API user
- TD SYNNEX uses this to link activities to your account

**User Name (API Key)**:
- Enter the username generated when you created your Autotask API user
- This is the unique identifier for your API access
- Copy and paste to avoid typing errors
- Case-sensitive - enter exactly as generated

**Secret (API Password)**:
- Enter the secret/password generated for your API user
- Use the eye icon to show/hide the password while typing
- This is only shown once in Autotask, so use your saved copy
- Case-sensitive and often contains special characters

### Authentication Tips

**Copy and Paste**: Always copy and paste credentials to avoid typing errors.

**Check for Extra Spaces**: Make sure there are no leading or trailing spaces.

**Verify Case Sensitivity**: API credentials are case-sensitive.

**Use Saved Credentials**: Use the credentials you saved when creating the API user.

### Complete the Connection

1. **Review Your Entries**
   - Double-check all fields are filled correctly
   - Verify the email matches your Autotask resource
   - Confirm credentials are exactly as generated

2. **Submit the Connection**
   - Click **Connect to Autotask**
   - TD SYNNEX will validate your credentials
   - This may take a few moments

3. **Handle Browser Requirements**
   - Ensure your browser allows pop-ups
   - Autotask may require zone confirmation
   - Follow any additional prompts that appear

## Step 3: Verify Successful Connection

### Connection Validation Process

When you submit your credentials, TD SYNNEX Digital Bridge:

1. **Tests API Connectivity** - Verifies it can reach your Autotask system
2. **Validates Credentials** - Confirms your username and secret are correct
3. **Checks Permissions** - Ensures your API user has necessary access
4. **Establishes Trust** - Creates a secure connection between systems

### Success Indicators

**Connection Status Changes**: The connector status updates to "Connected".

**Templates Become Available**: Integration templates appear and can be configured.

**No Error Messages**: The process completes without authentication errors.

**Confirmation Message**: You receive a success notification.

### If Connection Fails

**Common Issues and Solutions**:

**Authentication Failed**:
- Verify username and secret are correct
- Check that the API user is active in Autotask
- Ensure no extra spaces in credentials

**Permission Denied**:
- Confirm API user has proper security level
- Verify module access permissions
- Check line of business assignments

**Network Issues**:
- Verify internet connectivity
- Check firewall settings
- Ensure TLS 1.2 support

**Browser Problems**:
- Enable pop-ups for the Digital Bridge domain
- Try a different browser
- Clear browser cache and cookies

## Step 4: Review Integration Templates

### Available Templates

After successful connection, you'll see three integration templates:

**Product Sync**:
- Downloads TD SYNNEX products into your Autotask catalog
- Updates pricing and availability daily
- Foundation for other templates

**Submit Order**:
- Converts Autotask purchase orders into TD SYNNEX orders
- Automates the ordering process
- Handles order validation and submission

**Get Order Status**:
- Tracks TD SYNNEX order status in Autotask
- Updates shipping and tracking information
- Provides real-time order visibility

![Autotask Purchase Order Creation](/public/assets/images/autotask-new-purchase-order.png)

### Template Status

**Initially Disabled**: All templates start in a disabled state.

**Individual Configuration**: Each template must be configured separately.

**Dependencies**: Some templates work better when others are enabled first.

**Flexible Setup**: You can enable only the templates you need.

### Template Configuration Order

**Recommended Sequence**:

1. **Start with Product Sync** - This creates the foundation by adding TD SYNNEX products to your catalog
2. **Add Submit Order** - This enables automated ordering from Autotask
3. **Enable Get Order Status** - This provides order tracking and updates

**Why This Order Matters**:
- Product Sync must run before you can create orders with TD SYNNEX products
- Submit Order creates the orders that Get Order Status can track
- Each template builds on the capabilities of the previous ones

## Step 5: Plan Your Template Configuration

### Assess Your Needs

**Product Catalog Requirements**:
- How many TD SYNNEX products do you want in your catalog?
- Which product categories are most important to your business?
- Do you need daily updates or less frequent synchronization?

**Order Processing Preferences**:
- Do you want automatic order submission or manual control?
- How often should orders be processed?
- What approval workflows do you need?

**Status Tracking Needs**:
- How important is real-time order status?
- Do you need tracking numbers in Autotask?
- Should customers receive automatic updates?

### Resource Planning

**Staff Training**: Plan to train staff on new integration features.

**Process Changes**: Consider how the integration will change your workflows.

**Monitoring Setup**: Decide who will monitor integration performance.

**Support Procedures**: Establish procedures for handling integration issues.

## Understanding the Integration Architecture

### Data Flow Overview

**TD SYNNEX to Autotask**:
- Product information and specifications
- Current pricing and promotional rates
- Inventory levels and availability
- Order status and tracking details
- Invoice and shipping information

**Autotask to TD SYNNEX**:
- Purchase order details and line items
- Customer billing and shipping information
- Order quantities and specifications
- Special instructions and requirements

### Security and Reliability

**Encrypted Communications**: All data transfer uses secure HTTPS connections.

**Authentication Tokens**: API access uses secure token-based authentication.

**Error Handling**: Automatic retry mechanisms handle temporary failures.

**Logging**: Comprehensive logs track all integration activities.

**Monitoring**: Continuous monitoring ensures reliable operation.

## Next Steps

### Immediate Actions

1. **Verify Connection Status** - Confirm the connector shows "Connected"
2. **Review Template Options** - Understand what each template provides
3. **Plan Configuration** - Decide which templates to enable first
4. **Prepare Your Team** - Brief staff on upcoming changes

### Template Configuration

**Start with Product Sync**:
- This is the foundation for everything else
- See [Product Sync Template](./kb_autotask_template_product_sync.md) for detailed setup

**Add Order Automation**:
- Configure order submission when ready
- See [Submit Order Template](./kb_autotask_template_submit_order.md) for instructions

**Enable Status Tracking**:
- Set up order status monitoring
- See [Get Order Status Template](./kb_autotask_template_order_status.md) for details

### Ongoing Management

**Monitor Performance**: Regularly check integration logs and status.

**Update Credentials**: Refresh API credentials before they expire.

**Review Settings**: Periodically assess and adjust template configurations.

**Train Staff**: Ensure team members understand how to use new capabilities.

## Troubleshooting Connection Issues

### Common Problems and Solutions

**Connection Keeps Failing**:
- Verify all credentials are exactly correct
- Check that API user is active and has permissions
- Ensure network connectivity and firewall settings

**Templates Don't Appear**:
- Confirm connection was successful
- Refresh the browser page
- Check that your account has template access

**Intermittent Connection Issues**:
- Monitor network stability
- Check Autotask system status
- Review API rate limits and usage

**Permission Errors**:
- Verify API user security level
- Check module access permissions
- Confirm line of business assignments

### Getting Support

**TD SYNNEX Support**:
- Email: digitalbridge@tdsynnex.com
- Include connection details and error messages
- Provide API user information (not credentials)

**Autotask Support**:
- For Autotask-specific API issues
- User permission and configuration help
- System status and performance questions

**Self-Service Resources**:
- Digital Bridge documentation
- Integration guides and best practices
- Community forums and knowledge base

The connection between TD SYNNEX Digital Bridge and Autotask PSA is now established. You're ready to configure the integration templates and start automating your product catalog, ordering, and tracking processes.

