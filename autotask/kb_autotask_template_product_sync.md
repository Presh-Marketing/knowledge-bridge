# Product Sync Template

## What This Template Does

The Product Sync template is the foundation of your TD SYNNEX integration with Autotask PSA. It automatically downloads TD SYNNEX products into your Autotask product catalog, keeping your pricing and availability information current.

Think of this template as creating a bridge between the TD SYNNEX catalog and your Autotask system. Once enabled, it ensures that when you create quotes or purchase orders in Autotask, you're working with accurate, up-to-date TD SYNNEX product information.

### Key Benefits

**Always Current Information**: Your Autotask catalog stays synchronized with TD SYNNEX pricing and availability.

**Large Catalog Support**: Handles up to 20,000 SKUs per day with automatic updates.

**Automated Process**: Runs on schedule without manual intervention.

**Incremental Updates**: Only updates products that have changed, making the process efficient.

**Foundation for Other Templates**: Required for the Submit Order and Get Order Status templates to work properly.

## How Product Sync Works

### Daily Synchronization Process

1. **Connection**: The template connects to TD SYNNEX APIs using your Digital Bridge credentials
2. **Data Retrieval**: Downloads product information including SKUs, descriptions, pricing, and availability
3. **Category Mapping**: Applies your configured category mappings to organize products in Autotask
4. **Product Creation/Update**: Creates new products or updates existing ones in your Autotask catalog
5. **Inventory Updates**: Updates stock levels and pricing information
6. **Logging**: Records all activities for monitoring and troubleshooting

### What Gets Synchronized

**Product Information**:
- SKU numbers and manufacturer part numbers
- Product names and detailed descriptions
- Technical specifications and features
- Product categories and classifications

**Pricing Data**:
- Current TD SYNNEX pricing
- Promotional pricing and special offers
- Cost information for margin calculations
- Currency handling and conversions

**Availability Information**:
- Current stock levels at TD SYNNEX
- Availability status (in stock, backordered, discontinued)
- Lead times for out-of-stock items
- Regional availability variations

![Autotask Product Catalog with TD SYNNEX Products](/public/assets/images/autotask-product-catalog.png)

## Prerequisites for Product Sync

### System Requirements

**Autotask API Access**:
- API-only user with proper permissions
- Access to Product Catalog module
- Access to Inventory module
- Proper line of business assignments

**TD SYNNEX Requirements**:
- Active Digital Bridge connection
- Autotask connector enabled
- Appropriate product subscriptions

### Planning Your Product Catalog

**Category Strategy**:
- Decide how to organize TD SYNNEX products in Autotask
- Plan your category mapping approach
- Consider your existing product structure

**Business Unit Assignment**:
- Determine which business units should have access
- Plan for multi-location scenarios
- Consider departmental access needs

**Pricing Strategy**:
- Decide on markup and pricing rules
- Plan for promotional pricing handling
- Consider currency conversion needs

## Step 1: Configure Product Sync Settings

### Access the Configuration

1. **Navigate to Integration Templates**
   - Go to your TD SYNNEX Digital Bridge portal
   - Click on the Autotask connector
   - Select the **Integration Templates** tab

2. **Open Product Sync Settings**
   - Find the **Product Sync** template tile
   - Click **Change Settings** to open the configuration wizard
   - The wizard will guide you through the setup process

### Understanding the Configuration Wizard

The Product Sync configuration wizard has two main steps:

**Step 1**: Category mapping and product organization
**Step 2**: Pricing, inventory, and update options

Each step is important for ensuring products are properly organized and updated in your Autotask system.

## Step 2: Map Product Categories

### Why Category Mapping Matters

Category mapping determines how TD SYNNEX products are organized in your Autotask catalog. Proper mapping ensures:

- Products appear in logical categories
- Staff can find products easily
- Reporting and analysis work correctly
- Inventory management is organized

### Category Mapping Options

**Autotask Item Categories**:
- **Materials**: Physical hardware products
- **Service**: Software licenses and subscriptions
- **Labor**: Professional services
- **Expense**: Miscellaneous items

**Business Unit Assignment**:
- Assign products to specific business units
- Control access and visibility
- Support multi-location operations

### Mapping Strategy

**Hardware Products**:
- Map to **Materials** category
- Include computers, networking equipment, peripherals
- Consider subcategories for different hardware types

**Software Products**:
- Map to **Service** category
- Include licenses, subscriptions, cloud services
- Distinguish between one-time and recurring items

**Accessories and Supplies**:
- Map to **Materials** or **Expense** as appropriate
- Include cables, adapters, consumables
- Consider frequency of ordering

### Configuration Steps

1. **Review TD SYNNEX Categories**
   - The wizard shows available TD SYNNEX product categories
   - Each category represents a group of similar products
   - You'll map each to an Autotask category

2. **Select Autotask Categories**
   - Use dropdown menus to choose appropriate Autotask categories
   - Consider your existing catalog structure
   - Think about how staff will search for products

3. **Assign Business Units**
   - Choose which business units should have access
   - Consider departmental needs and restrictions
   - Plan for future organizational changes

4. **Review and Confirm**
   - Double-check all mappings before proceeding
   - Ensure categories make sense for your business
   - Click **Next** to continue to pricing options

## Step 3: Configure Pricing and Inventory Options

### Pricing Configuration

**Sync Cost and Inventory**:
- **Enable**: Updates Autotask with current TD SYNNEX pricing and stock levels
- **Disable**: Only imports SKUs and descriptions without pricing

**Currency Handling**:
- **Use Default Currency**: Converts all prices to your Autotask default currency
- **Use TD SYNNEX Currency**: Maintains original currency from TD SYNNEX

**Promotional Pricing**:
- **Include Promotions**: Updates products with current promotional pricing
- **Standard Pricing Only**: Uses regular pricing without promotions

### Inventory Management Options

**Stock Level Updates**:
- **Real-time Sync**: Updates Autotask inventory with TD SYNNEX availability
- **Threshold Management**: Sets minimum stock levels for reordering
- **Backorder Handling**: Manages products that are temporarily out of stock

**Update Frequency**:
- **Daily Updates**: Standard synchronization schedule
- **Custom Schedule**: Set specific times for updates
- **Manual Triggers**: Run updates on demand

### Product Update Behavior

**Update Existing Items**:
- **Overwrite Descriptions**: Replaces existing product descriptions with TD SYNNEX data
- **Preserve Custom Data**: Keeps your custom product information
- **Merge Information**: Combines TD SYNNEX data with existing information

**New Product Handling**:
- **Auto-Create**: Automatically adds new TD SYNNEX products
- **Review Required**: Requires approval before adding new products
- **Category Filtering**: Only adds products from selected categories

### Advanced Options

**Data Validation**:
- **Price Validation**: Checks for reasonable price changes
- **SKU Verification**: Ensures SKU formats are correct
- **Category Validation**: Confirms category mappings are valid

**Error Handling**:
- **Retry Failed Items**: Automatically retries failed product updates
- **Error Notifications**: Sends alerts for persistent failures
- **Logging Level**: Controls detail level of activity logs

## Step 4: Enable and Monitor Product Sync

### Enabling the Template

1. **Save Configuration**
   - Review all settings carefully
   - Click **Save** to apply your configuration
   - The wizard closes and returns to the templates page

2. **Activate the Template**
   - Find the Product Sync template tile
   - Use the toggle switch to turn it **On**
   - The template begins working immediately

3. **Initial Synchronization**
   - The first sync may take several hours
   - Progress is shown in the Sync Activity Log
   - Don't disable the template during initial sync

### Monitoring Sync Activity

**Sync Activity Log**:
- Shows real-time progress of synchronization
- Displays number of products processed
- Reports any errors or warnings
- Provides performance metrics

**Key Metrics to Watch**:
- **Products Processed**: Total number of products synchronized
- **New Products Added**: Count of products added to Autotask
- **Products Updated**: Count of existing products modified
- **Errors**: Any products that failed to sync
- **Processing Time**: How long the sync took to complete

### Understanding Sync Status

**Running**: Synchronization is currently in progress.

**Completed**: Sync finished successfully with no errors.

**Completed with Warnings**: Sync finished but some products had minor issues.

**Failed**: Sync encountered errors and couldn't complete.

**Scheduled**: Next sync is scheduled and waiting to run.

## Troubleshooting Product Sync

### Common Issues and Solutions

**No Products Syncing**:
- Verify API user has Product Catalog permissions
- Check category mappings are configured
- Ensure business unit assignments are correct
- Confirm TD SYNNEX product subscriptions are active

**Partial Product Updates**:
- Review error messages in Sync Activity Log
- Check for products with invalid data
- Verify Autotask system capacity and performance
- Consider reducing sync batch size

**Pricing Not Updating**:
- Confirm "Sync cost and inventory" is enabled
- Check currency configuration settings
- Verify API user has Inventory module access
- Review promotional pricing settings

**Category Assignment Problems**:
- Review category mapping configuration
- Check for missing or invalid Autotask categories
- Verify business unit access permissions
- Consider creating additional categories if needed

### Performance Optimization

**Large Catalog Management**:
- Use category filtering to limit product scope
- Schedule syncs during off-peak hours
- Monitor Autotask system performance
- Consider incremental sync strategies

**Network and Connectivity**:
- Ensure stable internet connection
- Monitor API rate limits and usage
- Check firewall and security settings
- Verify TLS/SSL certificate validity

**Data Quality**:
- Review product descriptions for accuracy
- Check SKU formats and consistency
- Validate pricing and currency information
- Monitor for duplicate products

## Best Practices for Product Sync

### Initial Setup

**Start Small**: Begin with a limited set of product categories to test the process.

**Test Thoroughly**: Run initial syncs during low-usage periods.

**Monitor Closely**: Watch the first few syncs carefully for issues.

**Document Settings**: Keep records of your configuration choices.

### Ongoing Management

**Regular Monitoring**: Check sync logs weekly for errors or warnings.

**Performance Review**: Monitor sync times and adjust schedules as needed.

**Category Maintenance**: Periodically review and update category mappings.

**User Training**: Ensure staff understand how to find and use synced products.

### Data Management

**Backup Strategy**: Maintain backups before major configuration changes.

**Change Control**: Document any changes to sync settings.

**Quality Assurance**: Regularly spot-check product data for accuracy.

**Cleanup Procedures**: Remove obsolete or discontinued products periodically.

## Integration with Other Templates

### Submit Order Template

Product Sync creates the foundation for automated ordering:
- Synced products can be used in purchase orders
- Current pricing ensures accurate order values
- Availability information prevents ordering out-of-stock items

### Get Order Status Template

Product information supports order tracking:
- Product details help identify order items
- SKU mapping ensures accurate status updates
- Inventory updates reflect order fulfillment

### Workflow Integration

**Quote Creation**: Staff can use current TD SYNNEX products and pricing in quotes.

**Order Processing**: Purchase orders use accurate product and pricing information.

**Inventory Management**: Stock levels reflect TD SYNNEX availability.

**Reporting**: Product data supports accurate sales and inventory reporting.

## Next Steps

### After Product Sync is Running

1. **Verify Product Data**: Check that products appear correctly in Autotask
2. **Train Your Team**: Show staff how to find and use TD SYNNEX products
3. **Configure Submit Order**: Set up automated ordering capabilities
4. **Enable Order Status**: Add order tracking and status updates

### Template Configuration Order

**Recommended Sequence**:
1. **Product Sync** (Foundation - start here)
2. **Submit Order** (Automated ordering)
3. **Get Order Status** (Order tracking)

### Ongoing Optimization

**Monitor Performance**: Track sync times and success rates.

**Adjust Categories**: Refine category mappings based on usage.

**Update Settings**: Modify configuration as business needs change.

**Expand Scope**: Add more product categories as you become comfortable with the process.

Product Sync is the cornerstone of your TD SYNNEX integration. Once it's running smoothly, you'll have a solid foundation for automated ordering and comprehensive order tracking in Autotask PSA.

