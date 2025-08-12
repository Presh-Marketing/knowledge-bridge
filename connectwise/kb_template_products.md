# Product Sync Template

## Overview

The Product Sync template is the foundation of your TD SYNNEX integration. It downloads TD SYNNEX products into your ConnectWise PSA product catalog, creating a local copy that you can use for quoting and ordering.

Think of this as building a bridge between the TD SYNNEX catalog and your ConnectWise system. Once this bridge is built, you can use TD SYNNEX products just like any other products in your system.

## Why You Need Product Sync

### Benefits of Syncing Products

**Accurate Product Information**: Get official TD SYNNEX product names, descriptions, and specifications directly from the source.

**Current Pricing**: Daily updates ensure your catalog reflects current TD SYNNEX pricing and availability.

**Streamlined Quoting**: Add TD SYNNEX products to opportunities just like any other products in your catalog.

**Automated Ordering**: Other templates can automatically submit orders because the products are properly mapped between systems.

**Reduced Errors**: Eliminate manual product entry and the mistakes that come with it.

### What Gets Synced

When you enable Product Sync, the template downloads:
- Product SKUs and descriptions
- Manufacturer information
- Product categories and subcategories
- Current pricing (updated daily)
- Availability status
- Product specifications and features
- Product images (when available)

![Product Catalog Sync Process](/public/assets/images/cw-product-catalog-sync.webp)

## Setting Up Product Sync

### Step 1: Enable the Template

1. **Access Integration Templates**
   - Log into TD SYNNEX Digital Bridge
   - Navigate to your ConnectWise PSA connector
   - Click on the "Integration Templates" tab

2. **Enable Product Sync**
   - Find the "Product Sync" template card
   - Toggle the switch to "Active"
   - The template will show a green status indicator

### Step 2: Select Product Categories

Choosing the right product categories is crucial because it determines which products appear in your ConnectWise catalog.

1. **Open Category Selection**
   - Click "Change Settings" on the Product Sync card
   - You'll see a tree view of available categories

2. **Choose Your Categories**
   - Expand category folders to see subcategories
   - Check the boxes for categories that match your business
   - Consider starting with a few key categories and expanding later

3. **Category Examples**
   - **Compute & Storage**: Servers, storage devices, memory
   - **Networking**: Switches, routers, wireless equipment
   - **Software**: Operating systems, productivity software, security
   - **Consumer Electronics**: Tablets, smartphones, accessories
   - **Components**: Processors, graphics cards, power supplies

### Step 3: Configure Sync Settings

**Sync Frequency**: The template automatically runs daily, typically during off-peak hours.

**Product Limits**: The template syncs up to 20,000 products. If you need more, contact TD SYNNEX for a custom price file.

**Vendor Filtering**: You can optionally filter by specific vendors within your selected categories.

## How Product Sync Works

### Daily Sync Process

Every day, the Product Sync template follows this process:

1. **Connect to TD SYNNEX API**: Establishes a secure connection to retrieve product data
2. **Download Product Information**: Gets details for all products in your selected categories
3. **Compare with Existing Products**: Checks what's already in your ConnectWise catalog
4. **Update Existing Products**: Refreshes pricing, availability, and descriptions
5. **Add New Products**: Creates catalog entries for new TD SYNNEX products
6. **Remove Discontinued Products**: Marks discontinued items as inactive
7. **Log Results**: Records the sync activity for your review

### Product Mapping

The template creates a connection between TD SYNNEX SKUs and ConnectWise products:
- **TD SYNNEX SKU**: The official TD SYNNEX product number
- **ConnectWise Product ID**: Your internal product identifier
- **Vendor Product Number**: Links the product to the TD SYNNEX vendor

This mapping is essential for other templates to work correctly.

### Handling Product Updates

When TD SYNNEX updates product information:
- **Price Changes**: Updated immediately in your catalog
- **Availability Changes**: Stock status reflects current TD SYNNEX inventory
- **Product Descriptions**: Enhanced descriptions and specifications are updated
- **New Variants**: New models or configurations are added automatically

## Managing Your Product Catalog

### Monitoring Sync Activity

**Sync Activity Log**: Check this regularly to see:
- When the last sync completed
- How many products were updated
- Any errors or warnings
- Performance metrics

**Success Indicators**:
- Green status on the Product Sync card
- Recent timestamp on last sync
- No error messages in the activity log

### Organizing Synced Products

**Product Categories**: TD SYNNEX products are organized into categories that match your selections.

**Vendor Assignment**: All synced products are automatically assigned to the TD SYNNEX vendor.

**Product Status**: New products are set to "Active" by default, discontinued products become "Inactive".

**Pricing Updates**: Product costs are updated daily, but you can set your own markup and selling prices.

### Customizing Product Information

While the sync maintains core product data, you can customize:
- **Selling Prices**: Set your markup over TD SYNNEX cost
- **Product Descriptions**: Add your own notes or selling points
- **Categories**: Move products to different categories if needed
- **Status**: Activate or deactivate products as needed

## Best Practices

### Category Selection Strategy

**Start Conservative**: Begin with categories you know well and expand gradually.

**Match Your Business**: Choose categories that align with your current sales focus.

**Consider Customer Demand**: Include categories your customers frequently request.

**Review Regularly**: Adjust category selections as your business evolves.

### Catalog Management

**Regular Reviews**: Monthly review of new products and categories.

**Pricing Strategy**: Develop consistent markup rules for different product types.

**Product Descriptions**: Enhance key products with additional selling information.

**Inventory Alignment**: Ensure your physical inventory processes align with the synced catalog.

### Performance Optimization

**Category Limits**: Don't sync more categories than you can effectively manage.

**Sync Monitoring**: Watch for performance issues and adjust categories if needed.

**Error Resolution**: Address sync errors promptly to maintain data quality.

**Team Training**: Ensure your team understands how to use the synced products.

## Troubleshooting Common Issues

### Sync Failures

**Problem**: Product sync fails to complete
**Causes**: 
- API connectivity issues
- Too many products selected
- ConnectWise system limitations

**Solutions**:
- Check internet connectivity
- Reduce the number of selected categories
- Contact support if issues persist

### Missing Products

**Problem**: Expected products don't appear in ConnectWise
**Causes**:
- Products not in selected categories
- Products discontinued by TD SYNNEX
- Category selection too narrow

**Solutions**:
- Review and expand category selections
- Check TD SYNNEX catalog for product availability
- Verify category mappings are correct

### Pricing Issues

**Problem**: Product prices seem incorrect
**Causes**:
- Pricing tier differences
- Currency conversion issues
- Sync timing problems

**Solutions**:
- Verify your TD SYNNEX pricing tier
- Check for recent price changes
- Trigger a manual sync to refresh prices

### Performance Problems

**Problem**: Sync takes too long or times out
**Causes**:
- Too many products selected
- Network connectivity issues
- ConnectWise system performance

**Solutions**:
- Reduce the number of categories
- Schedule syncs during off-peak hours
- Contact support for performance optimization

## Advanced Configuration

### Custom Price Files

For catalogs larger than 20,000 products:

1. **Request Price File**: Contact TD SYNNEX support for a custom price file template
2. **Complete Template**: Fill in the required product information
3. **Upload File**: Submit the completed file through TD SYNNEX support
4. **Bulk Import**: The support team will perform a bulk import of your products

### Integration with Other Templates

**Price & Availability**: Requires Product Sync to identify which products to check
**Create Orders**: Uses product mapping created by Product Sync
**Order Status**: Tracks orders for products synced through this template

### API Rate Limits

The Product Sync template respects TD SYNNEX API rate limits:
- **Daily Limits**: Designed to stay within daily API quotas
- **Retry Logic**: Automatically retries failed requests
- **Error Handling**: Gracefully handles temporary API issues

## Monitoring and Maintenance

### Daily Checks

- Review sync status in the activity log
- Check for any error messages
- Verify that new products are appearing correctly

### Weekly Reviews

- Analyze which products are being added or removed
- Review pricing changes and their impact
- Check category performance and usage

### Monthly Maintenance

- Evaluate category selections for optimization
- Review product catalog organization
- Assess sync performance and timing
- Plan for any needed adjustments

## Next Steps

Once Product Sync is working well:

1. **Enable Price & Availability**: Get real-time pricing for quotes
2. **Test Product Usage**: Create test opportunities with synced products
3. **Train Your Team**: Show users how to find and use TD SYNNEX products
4. **Monitor Usage**: Track which products are most popular
5. **Expand Gradually**: Add more categories as you become comfortable with the system

The Product Sync template is your foundation for a streamlined TD SYNNEX integration. Take time to set it up correctly, and it will serve you well for all your future TD SYNNEX business.

