# Prerequisites & API Setup

## What You Need Before Starting

Before you can connect TD SYNNEX Digital Bridge to Autotask PSA, you need to gather some important information and set up a few things in both systems. Autotask PSA has specific requirements for API access that are different from other PSA systems.

### TD SYNNEX Requirements

You need a valid TD SYNNEX account to use this integration. Specifically, you must have:

- **TD SYNNEX Electronic Commerce (EC) account** - This is your regular TD SYNNEX login
- **Access to TD SYNNEX Digital Bridge** - Your account must be enabled for Digital Bridge
- **Autotask PSA connector enabled** - Contact TD SYNNEX support if you don't see Autotask PSA in your Connector Bridge

### Autotask PSA Requirements

Autotask PSA has specific requirements for API access that are more restrictive than other systems. You need to create a dedicated API-only user account that cannot log into the regular Autotask interface.

## Understanding Autotask API Users

### Why API-Only Users Are Required

Autotask PSA requires all API access to use dedicated API-only user accounts. These accounts:

- **Cannot log into the Autotask web interface** - They are API access only
- **Have full system administrator access via API** - But only through API calls
- **Are not charged per seat** - There's no additional cost for API-only users
- **Have no limit on quantity** - You can create as many as needed
- **Require a tracking identifier** - Each API user must have a unique identifier

### API User vs Regular User

**Regular Autotask Users**:
- Can log into the web interface
- Have limited API access
- Count against your seat licenses
- May have restricted permissions

**API-Only Users**:
- Cannot log into the web interface
- Have full API access with proper permissions
- Don't count against seat licenses
- Designed specifically for integrations

## Creating Your Autotask API User

### Step 1: Access User Management

1. **Log in as an Administrator**
   - Only administrators can create API users
   - Use your regular Autotask login

2. **Navigate to User Management**
   - Go to **Admin → Resources/Users**
   - Or **Integration Center → Add API User** (depending on your Autotask version)
   - Click **New API User**

### Step 2: Configure Basic Information

**User Details**:
- **First Name**: TD SYNNEX
- **Last Name**: Integration
- **Email Address**: Use your administrator email address
- **Security Level**: Select **API User (API-only)**

**Important**: The security level **API User (API-only)** is crucial. This provides full API access while preventing web interface login.

### Step 3: Set Up Tracking Identifier

**What is a Tracking Identifier?**
The tracking identifier (also called ApiIntegrationCode) distinguishes between different integrations and is required for all API requests.

**Setting the Identifier**:
1. Go to the **Security** tab
2. Assign a **tracking identifier**
3. Choose the TD SYNNEX vendor identifier if available
4. Or create a custom identifier like "TDSYNNEX_INTEGRATION"

### Step 4: Generate API Credentials

**Generate Username and Secret**:
1. Click **Generate Key** (may be labeled "User Name")
2. This creates the API user's unique username
3. Click **Generate Secret** to create the password
4. **Copy both values immediately** - they won't be shown again
5. Store them securely - you'll need them for the integration

**Important Security Note**: The secret (password) is only shown once. If you lose it, you'll need to generate a new one.

### Step 5: Configure Permissions and Access

**Line of Business Assignment**:
- Ensure the API user is assigned to the correct line of business
- Without proper assignments, API calls may return no results
- The user needs access to all relevant business units

**Module Access**:
The API user needs access to specific Autotask modules for the integration to work properly.

## Required Permissions for TD SYNNEX Integration

### Essential Module Access

The integration requires access to these Autotask modules:

| Module | Access Level | Purpose | Why It's Needed |
|--------|-------------|---------|-----------------|
| **Product Catalog** | Read/Write | Product management | Create and update TD SYNNEX products in your catalog |
| **Inventory** | Read/Write | Stock management | Update quantities and pricing information |
| **Purchase Orders** | Full Access | Order processing | Create, update, and track purchase orders |
| **Purchase Order Line Items** | Full Access | Order details | Manage individual products within orders |
| **Companies/Contacts** | Read | Customer information | Access billing and shipping details for orders |
| **User-Defined Fields** | Update | Custom data | Store TD SYNNEX-specific tracking information |

### Detailed Permission Requirements

**Product Catalog Access**:
- **Create**: Add new TD SYNNEX products to your catalog
- **Read**: Access existing product information
- **Update**: Modify pricing, descriptions, and availability
- **Purpose**: Maintains up-to-date TD SYNNEX product information

**Purchase Order Management**:
- **Create**: Generate new purchase orders for TD SYNNEX
- **Read**: Access order information for status updates
- **Update**: Modify orders and add tracking information
- **Delete**: Remove or cancel orders when necessary
- **Purpose**: Complete order lifecycle management

**Inventory Control**:
- **Read**: Check current stock levels
- **Update**: Adjust quantities based on TD SYNNEX availability
- **Purpose**: Accurate inventory tracking and availability

**Customer Information**:
- **Read**: Access company and contact details
- **Purpose**: Proper billing and shipping for orders

## API Authentication Setup

### Understanding Autotask API Authentication

Autotask uses header-based authentication for API requests. Each request must include specific HTTP headers:

**Required Headers**:
- **ApiIntegrationCode**: Your tracking identifier
- **UserName**: The generated API username
- **Secret**: The generated API password
- **Content-Type**: application/json (for JSON requests)

### Security Requirements

**TLS Encryption**: All API requests must use TLS 1.2 or higher encryption.

**No Single Sign-On**: Autotask API does not support SSO authentication.

**Direct Authentication**: Each request must include the authentication headers.

**Session Management**: The API is stateless - no session management required.

## Integration Features and Capabilities

### What the Integration Provides

**Daily Catalog Sync**:
- Up to 20,000 TD SYNNEX SKUs synchronized daily
- Current pricing, availability, and promotions
- Automatic updates to keep your catalog current

![Autotask Product Catalog with TD SYNNEX Products](/public/assets/images/autotask-product-catalog.png)

**Flexible Order Automation**:
- Manual order submission
- Scheduled automatic ordering
- Custom workflow triggers
- Single-click conversion from opportunities to TD SYNNEX orders

**Complete Order Tracking**:
- Real-time status updates
- Shipping and tracking information
- Invoice details and references
- Automatic status synchronization

![Autotask Purchase Orders](/public/assets/images/autotask-purchase-order-list.png)

**Error Handling and Logging**:
- Detailed error logs for troubleshooting
- Automatic retry for transient failures
- Comprehensive activity tracking

### Data Flow Overview

**TD SYNNEX to Autotask**:
- Product catalog (SKUs, descriptions, specifications)
- Pricing and promotional information
- Inventory levels and availability
- Order status and tracking numbers
- Invoice and reference information

**Autotask to TD SYNNEX**:
- Purchase orders with complete details
- Customer shipping and billing information
- Order quantities and specifications
- Special instructions and requirements

## Preparing for Integration

### Pre-Integration Checklist

**TD SYNNEX Account Verification**:
- ✅ Authorized TD SYNNEX partner status
- ✅ Digital Bridge portal access
- ✅ Autotask connector enabled in Connector Bridge
- ✅ Appropriate permissions for integration management

**Autotask System Preparation**:
- ✅ API-only user created with proper security level
- ✅ Tracking identifier assigned and recorded
- ✅ API credentials generated and securely stored
- ✅ Module permissions configured correctly
- ✅ Line of business assignments completed

![Autotask Account Search with TD SYNNEX](/public/assets/images/autotask-account-search.png)

**Network and Security**:
- ✅ Internet connectivity verified
- ✅ Firewall rules allow API traffic
- ✅ TLS 1.2 support confirmed
- ✅ Security policies reviewed and approved

### Testing API Access

Before proceeding with the full integration, test your API setup:

**Basic Connectivity Test**:
1. Use the API credentials to make a simple test call
2. Verify authentication works correctly
3. Confirm module access is functioning
4. Test data retrieval and updates

**Permission Validation**:
1. Test product catalog access
2. Verify purchase order creation capability
3. Confirm inventory update permissions
4. Validate customer information access

## Common Setup Issues and Solutions

### API User Creation Problems

**Problem**: Cannot create API-only user
**Solution**: Verify you're logged in as an administrator with user management permissions

**Problem**: Security level options missing
**Solution**: Check your Autotask version and permissions - contact Autotask support if needed

**Problem**: Tracking identifier rejected
**Solution**: Use a unique identifier that hasn't been used before

### Permission and Access Issues

**Problem**: API calls return no data
**Solution**: Check line of business assignments and module permissions

**Problem**: Authentication failures
**Solution**: Verify API credentials are correct and the user is active

**Problem**: Limited functionality
**Solution**: Review and expand module access permissions as needed

### Network and Connectivity Issues

**Problem**: Cannot connect to Autotask API
**Solution**: Check firewall settings and TLS support

**Problem**: Intermittent connection failures
**Solution**: Verify network stability and DNS resolution

**Problem**: Slow API responses
**Solution**: Check network latency and Autotask system performance

## Security Best Practices

### Credential Management

**Secure Storage**: Store API credentials in a secure, encrypted location.

**Access Control**: Limit access to API credentials to authorized personnel only.

**Regular Rotation**: Consider rotating API credentials periodically for security.

**Monitoring**: Monitor API usage for unusual activity or unauthorized access.

### Network Security

**Encrypted Connections**: Always use HTTPS/TLS for API communications.

**Firewall Configuration**: Configure firewalls to allow only necessary API traffic.

**IP Restrictions**: Consider restricting API access to specific IP addresses if possible.

**Logging**: Enable comprehensive logging for security monitoring and troubleshooting.

## Next Steps

Once you have completed the prerequisites:

1. **Verify All Requirements**: Double-check that all prerequisites are met
2. **Test API Access**: Perform basic API connectivity tests
3. **Proceed to Connection**: Move to [Connecting & Activating the Connector](./kb_autotask_connect_activation.md)
4. **Plan Template Configuration**: Review which integration templates you'll need
5. **Prepare Your Team**: Ensure staff understand the new integration capabilities

## Support and Resources

### Getting Help

**TD SYNNEX Support**:
- Email: digitalbridge@tdsynnex.com
- Digital Bridge portal support section
- Comprehensive documentation and guides

**Autotask Support**:
- For Autotask-specific API questions
- User management and permissions help
- System configuration assistance

### Additional Resources

**Documentation**:
- Autotask API documentation
- TD SYNNEX Digital Bridge guides
- Integration best practices

**Training**:
- Available through TD SYNNEX
- Autotask API training resources
- Custom training sessions upon request

The foundation you build with proper prerequisites and API setup determines the success of your entire integration. Take time to get this right, and the rest of the process will go smoothly.

