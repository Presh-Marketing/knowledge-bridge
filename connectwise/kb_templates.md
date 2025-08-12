# Integration Templates

## Understanding Templates

Integration templates are pre-built workflows that handle specific parts of your TD SYNNEX and ConnectWise PSA integration. Think of them as specialized tools that each do one job really well.

Each template can be turned on or off independently, so you can use only the features you need. However, some templates work better together - for example, you'll want Product Sync enabled before using the other templates.

## Template Overview

Here's what each template does and how they work together:

| Template | What It Does | When to Use It | Dependencies |
|----------|--------------|----------------|--------------|
| **Product Sync** | Downloads TD SYNNEX products into your ConnectWise catalog | Always - this is the foundation | None |
| **Get Product Price & Availability** | Updates pricing in real-time when quoting | When you want current pricing in quotes | Product Sync |
| **Create Orders from ConnectWise** | Automatically submits purchase orders to TD SYNNEX | When you want automated ordering | Product Sync |
| **Get Order Status** | Tracks order status and shipping information | When you want automatic status updates | Create Orders |

## Template 1: Product Sync

### What This Template Does

Product Sync downloads TD SYNNEX products into your ConnectWise product catalog. This creates a local copy of TD SYNNEX products that you can use in opportunities and purchase orders.

![Product Catalog with TD SYNNEX Products](/public/assets/images/cw-product-catalog.png)

### Key Features

- **Daily Automatic Sync**: Updates your catalog every day with new products and pricing
- **Up to 20,000 Products**: Syncs a large portion of the TD SYNNEX catalog
- **Category Filtering**: Choose which product categories to include
- **Vendor Filtering**: Select specific vendors if desired
- **Price File Import**: For larger catalogs, request a custom price file from TD SYNNEX

### Configuration Steps

1. **Enable the Template**
   - Go to Integration Templates
   - Toggle "Product Sync" to Active
   - The template starts working immediately

2. **Select Product Categories**
   - Click "Change Settings" on the Product Sync card
   - Use the category tree to select which products to sync
   - Choose categories that match your business focus
   - Save your selections

3. **Set Sync Schedule**
   - The template automatically runs daily
   - You can trigger manual syncs from the Sync Activity Log
   - Initial sync may take several hours for large catalogs

### How It Works

The Product Sync template:
1. Connects to the TD SYNNEX API every day
2. Downloads product information for your selected categories
3. Creates or updates products in your ConnectWise catalog
4. Maintains the link between ConnectWise products and TD SYNNEX SKUs
5. Updates pricing, availability, and product descriptions

### Best Practices

- **Start Small**: Begin with a few categories and expand as needed
- **Monitor the Sync Log**: Check for any errors or warnings
- **Review New Products**: Periodically check what new products have been added
- **Update Categories**: Adjust your category selections as your business changes

## Template 2: Get Product Price & Availability

### What This Template Does

This template provides real-time TD SYNNEX pricing and stock availability when you're creating opportunities in ConnectWise PSA. Instead of using outdated catalog prices, you get current market pricing.

### Key Features

- **Real-Time Pricing**: Gets current TD SYNNEX prices when you need them
- **Stock Availability**: Shows how many units are available
- **Automatic Updates**: Works seamlessly with your existing quoting process
- **Pre-Order Validation**: Ensures products are available before submitting orders

### Configuration Steps

1. **Enable the Template**
   - Go to Integration Templates
   - Toggle "Get Product Price & Availability" to Active
   - No additional configuration needed

2. **Using in Opportunities**
   - Add TD SYNNEX products to an opportunity
   - Set the "TDS Sync Price" field to "Get TDS Price"
   - Wait a few minutes for the price update
   - The field will change to "TDS Price Updated" when complete

### How It Works

When you trigger a price sync:
1. ConnectWise sends the product list to TD SYNNEX
2. TD SYNNEX returns current pricing and availability
3. ConnectWise updates the opportunity with new prices
4. You can see which products are in stock and which aren't

### Best Practices

- **Check Prices Before Quoting**: Always sync prices for important quotes
- **Monitor Availability**: Pay attention to stock levels for large orders
- **Update Before Ordering**: Sync prices again before converting to a purchase order
- **Use for Competitive Quotes**: Get the most current pricing for competitive situations

## Template 3: Create Orders from ConnectWise

### What This Template Does

This template automatically converts your ConnectWise sales orders into TD SYNNEX purchase orders. When you mark an opportunity as "Won" and create a sales order, the integration handles the rest.

![Purchase Orders with TD SYNNEX](/public/assets/images/cw-purchase-orders-list.png)

### Key Features

- **Automatic Order Submission**: Converts sales orders to purchase orders every 30 minutes
- **Order Number Tracking**: Updates ConnectWise with the TD SYNNEX order number
- **Error Handling**: Retries failed orders and logs any issues
- **Status Updates**: Keeps you informed of order progress

### Configuration Steps

1. **Enable the Template**
   - Go to Integration Templates
   - Toggle "Create Orders from ConnectWise" to Active
   - The template starts monitoring for new sales orders

2. **Prepare Your Sales Orders**
   - Ensure all products in the sales order are TD SYNNEX products
   - Verify shipping and billing information is complete
   - Set the purchase order status to "Send to TDS"

![Send to TDS Status](/public/assets/images/cw-send-to-tds-status.png)

### How It Works

Every 30 minutes, the template:
1. Looks for sales orders marked "Send to TDS"
2. Validates the order information
3. Submits the order to TD SYNNEX
4. Updates the ConnectWise purchase order with:
   - TD SYNNEX order number
   - Order acknowledgment status
   - Any error messages if the order fails

### Best Practices

- **Verify Product Mapping**: Ensure all products are properly synced TD SYNNEX items
- **Complete Shipping Info**: Make sure shipping addresses are accurate and complete
- **Monitor Order Status**: Check the Sync Activity Log for any failed orders
- **Handle Errors Quickly**: Address any order errors promptly to avoid delays

## Template 4: Get Order Status

### What This Template Does

This template monitors your TD SYNNEX orders and updates the corresponding ConnectWise purchase orders with shipping status, tracking numbers, and delivery information.

![Purchase Order Detail with Tracking](/public/assets/images/cw-purchase-order-detail.png)

### Key Features

- **Automatic Status Updates**: Monitors orders and updates status in real-time
- **Tracking Information**: Adds tracking numbers and shipping details
- **Multiple Status Types**: Handles all order states from processing to delivered
- **Invoice Information**: Updates with invoice numbers and dates

### Configuration Steps

1. **Enable the Template**
   - Go to Integration Templates
   - Toggle "Get Order Status" to Active
   - The template starts monitoring immediately

2. **Mark Orders for Tracking**
   - Set the "Send to TDS" field to "true" on purchase orders you want tracked
   - This can be done manually or automatically via the Create Orders template

### How It Works

The template regularly checks TD SYNNEX for updates on your orders and updates the ConnectWise purchase order status:

- **TDS Accepted**: Order has been received and accepted by TD SYNNEX
- **TDS Released**: Order has been released for processing
- **TDS Shipped**: Order has been shipped with tracking information
- **TDS Invoiced**: Order has been invoiced with invoice details
- **TDS Closed**: Order is complete

### Order Status Lifecycle

1. **Send to TDS**: You mark the order for submission
2. **TDS Accepted**: TD SYNNEX confirms receipt of the order
3. **TDS Released**: Order is released for fulfillment
4. **TDS Shipped**: Order ships with tracking number
5. **TDS Invoiced**: Invoice is generated
6. **TDS Closed**: Order is complete

### Best Practices

- **Enable for All Orders**: Set "Send to TDS" to true for all TD SYNNEX orders
- **Monitor Status Changes**: Watch for status updates in your purchase orders
- **Use Tracking Numbers**: Provide tracking information to your customers
- **Review Closed Orders**: Verify that completed orders match your expectations

## Template Combinations

### Recommended Setup for Most Users

1. **Start with Product Sync**: This is essential for everything else
2. **Add Price & Availability**: Get real-time pricing for quotes
3. **Enable Create Orders**: Automate the ordering process
4. **Add Order Status**: Track orders automatically

### Advanced Configuration

For high-volume users or those with specific needs:

- **Custom Category Selection**: Fine-tune which products to sync
- **Price File Import**: For catalogs larger than 20,000 products
- **Custom Workflows**: Set up ConnectWise workflows to trigger specific actions
- **Error Monitoring**: Set up alerts for failed orders or sync issues

## Monitoring and Maintenance

### Sync Activity Log

The Sync Activity Log shows:
- When each template last ran
- How many records were processed
- Any errors or warnings
- Performance metrics

### Regular Maintenance Tasks

- **Weekly**: Review the Sync Activity Log for errors
- **Monthly**: Check that product categories are still appropriate
- **Quarterly**: Review order success rates and address any patterns
- **As Needed**: Update API credentials if they expire

## Troubleshooting Templates

### Common Issues

**Template Won't Enable**
- Check that prerequisites are met
- Verify API permissions are correct
- Review connection status

**Products Not Syncing**
- Verify category selections
- Check for API rate limits
- Review error messages in the log

**Orders Not Submitting**
- Ensure products are properly mapped
- Verify shipping information is complete
- Check for missing required fields

**Status Updates Not Working**
- Confirm "Send to TDS" field is set correctly
- Verify order numbers match between systems
- Check for API connectivity issues

## Next Steps

With your templates configured, you're ready to:

1. **Test the Full Workflow**: Create a test opportunity and follow it through to order completion
2. **Train Your Team**: Show users how to use the new features
3. **Monitor Performance**: Keep an eye on the Sync Activity Log
4. **Optimize Settings**: Adjust categories and settings based on usage

For detailed instructions on each template, see the individual template articles:
- [Product Sync Template](./kb_template_products.md)
- [Get Product Price & Availability Template](./kb_template_price_availability.md)
- [Create Orders Template](./kb_template_create_orders.md)
- [Get Order Status Template](./kb_template_order_status.md)

