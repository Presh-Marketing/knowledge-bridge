# Get Product Price & Availability Template

## Overview

The Get Product Price & Availability template gives you real-time TD SYNNEX pricing and stock information when you're creating quotes in ConnectWise PSA. Instead of relying on yesterday's prices, you get current market pricing and availability at the moment you need it.

This template works seamlessly with your existing quoting process. When you add TD SYNNEX products to an opportunity, you can trigger a price check that updates all the pricing and availability information in real-time.

## Why Real-Time Pricing Matters

### The Problem with Static Pricing

**Outdated Information**: Product catalogs can become outdated quickly, especially in fast-moving technology markets.

**Competitive Disadvantage**: Using old prices can make your quotes less competitive or cause you to lose money on deals.

**Availability Issues**: You might quote products that are out of stock, leading to delays and customer dissatisfaction.

**Manual Checking**: Without automation, checking current prices means switching between systems and manual lookups.

### Benefits of Real-Time Pricing

**Current Market Prices**: Get the exact pricing that TD SYNNEX has right now, including any current promotions or special pricing.

**Stock Availability**: Know immediately if products are in stock and how many units are available.

**Competitive Quotes**: Ensure your quotes reflect the most current pricing for competitive situations.

**Reduced Errors**: Eliminate the guesswork and manual errors that come with outdated pricing.

**Faster Quoting**: Get pricing updates in minutes instead of hours or days.

## How the Template Works

### Integration with Opportunities

The template integrates directly with your ConnectWise opportunity process:

1. **Add Products**: Add TD SYNNEX products to your opportunity as usual
2. **Trigger Price Check**: Set the "TDS Sync Price" field to "Get TDS Price"
3. **Wait for Update**: The system contacts TD SYNNEX and retrieves current information
4. **Review Results**: Prices and availability are updated in your opportunity
5. **Continue Quoting**: Use the updated information to complete your quote

![Opportunity Price Sync Process](/public/assets/images/cw-opportunity-price-sync.webp)

### What Information Gets Updated

When you trigger a price check, the template updates:

**Product Pricing**:
- Current TD SYNNEX cost
- Any promotional pricing
- Volume discounts (if applicable)
- Special pricing tiers

**Availability Information**:
- Current stock levels
- Expected restock dates (if out of stock)
- Backorder status
- Alternative product suggestions

**Product Details**:
- Updated product descriptions
- Current specifications
- Manufacturer information
- Product lifecycle status

## Setting Up Price & Availability

### Prerequisites

Before enabling this template:
- **Product Sync must be active**: This template only works with products that have been synced
- **API connection verified**: Your ConnectWise API connection must be working
- **Proper permissions**: Your API user needs access to opportunities and products

### Enabling the Template

1. **Access Integration Templates**
   - Go to your ConnectWise PSA connector in Digital Bridge
   - Click on the "Integration Templates" tab

2. **Enable the Template**
   - Find "Get Product Price & Availability"
   - Toggle the switch to "Active"
   - The template is immediately ready to use

3. **No Additional Configuration**
   - This template works out of the box
   - No settings to configure
   - No schedules to set up

## Using Real-Time Pricing

### In Opportunities

**Step 1: Create or Open an Opportunity**
- Create a new opportunity or open an existing one
- Make sure you're working with TD SYNNEX products (synced products)

**Step 2: Add Products**
- Add TD SYNNEX products to your opportunity
- You can add multiple products at once
- The system will check pricing for all TD SYNNEX products in the opportunity

**Step 3: Trigger Price Check**
- Look for the "TDS Sync Price" field on the opportunity
- Change the value from "None" to "Get TDS Price"
- Save the opportunity

**Step 4: Wait for Update**
- The system will contact TD SYNNEX (usually takes 1-3 minutes)
- The "TDS Sync Price" field will change to "Processing" while working
- When complete, it will show "TDS Price Updated"

**Step 5: Review Updated Information**
- Check the updated product prices
- Review availability information
- Note any products that are out of stock
- Use this information to finalize your quote

### Best Practices for Using Price Checks

**Before Important Quotes**: Always check prices before submitting competitive quotes.

**Large Orders**: Verify availability for large quantity orders.

**Time-Sensitive Deals**: Check prices again if significant time has passed since the last check.

**Multiple Vendors**: If you're comparing TD SYNNEX to other vendors, get current TD SYNNEX pricing first.

**Before Converting to Orders**: Check prices one more time before converting opportunities to purchase orders.

## Understanding Price Updates

### Types of Price Changes

**Standard Pricing Updates**:
- Regular price adjustments from manufacturers
- Market-driven price changes
- Currency fluctuation impacts

**Promotional Pricing**:
- Limited-time manufacturer promotions
- Volume discount opportunities
- Special pricing events

**Availability Changes**:
- Stock level updates
- Backorder notifications
- Discontinued product alerts

### Price Check Results

**Successful Updates**: When the price check completes successfully:
- Product costs are updated with current TD SYNNEX pricing
- Availability status shows current stock levels
- The "TDS Sync Price" field shows "TDS Price Updated"
- You can proceed with confidence

**Partial Updates**: Sometimes only some products can be updated:
- Products in stock get current pricing
- Out-of-stock products may show limited information
- Discontinued products are flagged
- You'll need to review each product individually

**Failed Updates**: If the price check fails:
- The "TDS Sync Price" field will show an error status
- Check your internet connection and API status
- Try again in a few minutes
- Contact support if problems persist

## Advanced Features

### Bulk Price Checking

For opportunities with many products:
- The template checks all TD SYNNEX products at once
- Large product lists may take longer to process
- You'll get a summary of what was updated
- Individual product status is available in the product details

### Integration with Quoting Workflow

**Automated Workflows**: You can set up ConnectWise workflows to:
- Automatically trigger price checks when opportunities reach certain stages
- Send notifications when price updates are complete
- Flag opportunities that need price updates

**Quote Templates**: Incorporate price checking into your standard quoting process:
- Include price check steps in your quote templates
- Train staff to always check prices before finalizing quotes
- Set up reminders for periodic price updates on long-running opportunities

### Error Handling and Retries

**Automatic Retries**: The template automatically retries failed price checks:
- Network timeouts are retried automatically
- API rate limit issues are handled gracefully
- Temporary TD SYNNEX system issues are retried

**Error Logging**: All price check activities are logged:
- Successful updates are recorded with timestamps
- Errors are logged with specific error messages
- You can review the activity log to troubleshoot issues

## Monitoring and Troubleshooting

### Checking Template Status

**Template Health**: Monitor the template status in Digital Bridge:
- Green status indicates everything is working
- Yellow status may indicate minor issues
- Red status requires immediate attention

**Activity Log**: Review the activity log regularly:
- See how many price checks are being performed
- Identify any patterns in errors
- Monitor response times and performance

### Common Issues and Solutions

**Price Check Doesn't Start**
- Verify the opportunity contains TD SYNNEX products
- Check that the "TDS Sync Price" field is set correctly
- Ensure the template is enabled and active

**Price Check Takes Too Long**
- Large product lists take longer to process
- Network issues can cause delays
- Try checking smaller groups of products

**Some Products Don't Update**
- Products may be discontinued or out of stock
- Check individual product status in TD SYNNEX
- Verify products are still in your synced categories

**Pricing Seems Incorrect**
- Verify your TD SYNNEX pricing tier
- Check for recent manufacturer price changes
- Contact TD SYNNEX if pricing appears wrong

### Performance Optimization

**Timing Your Price Checks**:
- Avoid peak hours when possible
- Check prices during business hours for best response times
- Don't check prices more often than necessary

**Managing Large Opportunities**:
- Break large product lists into smaller groups
- Focus on high-value or critical products first
- Use bulk operations efficiently

## Integration with Other Templates

### Product Sync Dependency

The Price & Availability template requires Product Sync because:
- It only works with products that have been synced from TD SYNNEX
- Product mapping is essential for accurate price lookups
- Synced products have the necessary TD SYNNEX identifiers

### Create Orders Integration

When used with the Create Orders template:
- Price checks ensure orders are submitted with current pricing
- Availability checks prevent orders for out-of-stock items
- The combination provides a complete quote-to-order workflow

### Order Status Integration

Price checking complements order status tracking:
- Current pricing helps with reorders and follow-up sales
- Availability information supports customer service inquiries
- Combined data provides a complete customer view

## Best Practices Summary

### Daily Operations

- Check prices for all competitive quotes
- Verify availability for large orders
- Update long-running opportunities periodically
- Monitor the activity log for issues

### Weekly Reviews

- Review price check frequency and patterns
- Identify products that frequently have price changes
- Assess the impact of real-time pricing on your quotes
- Train staff on any new features or processes

### Monthly Analysis

- Analyze how real-time pricing affects your win rates
- Review pricing accuracy and customer feedback
- Evaluate the template's impact on your quoting process
- Plan for any needed adjustments or training

## Next Steps

With real-time pricing working effectively:

1. **Train Your Sales Team**: Show them how to use price checking in their daily workflow
2. **Integrate with Workflows**: Set up automated price checking in your standard processes
3. **Enable Create Orders**: Automate the next step in the process
4. **Monitor Results**: Track how real-time pricing improves your quoting accuracy
5. **Expand Usage**: Use price checking for more opportunities and product types

Real-time pricing gives you a significant competitive advantage by ensuring your quotes are always based on current market conditions. Use this capability to win more deals and improve your customer relationships.

