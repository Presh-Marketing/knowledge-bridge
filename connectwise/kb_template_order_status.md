# Get Order Status Template

## Overview

The Get Order Status template automatically monitors your TD SYNNEX orders and updates the corresponding ConnectWise purchase orders with current status, tracking information, and delivery details. This keeps your team and customers informed about order progress without manual checking.

Once an order is submitted to TD SYNNEX, this template takes over to track it through the entire fulfillment process - from acceptance through shipping to final delivery. All status updates appear automatically in your ConnectWise purchase orders.

## Why Automated Order Tracking Matters

### The Manual Tracking Problem

**Time-Consuming Lookups**: Without automation, checking order status requires logging into TD SYNNEX systems and manually searching for each order.

**Inconsistent Updates**: Manual checking leads to inconsistent information and gaps in status updates.

**Customer Service Delays**: When customers call for updates, you have to stop what you're doing to look up order information.

**Missed Status Changes**: Important status changes like shipping notifications can be missed without regular monitoring.

**Multiple System Management**: Keeping information synchronized between TD SYNNEX and ConnectWise requires constant attention.

### Benefits of Automated Status Tracking

**Real-Time Updates**: Order status changes appear in ConnectWise as soon as they happen in TD SYNNEX systems.

**Complete Visibility**: See the entire order lifecycle from acceptance to delivery in one place.

**Proactive Customer Service**: Know about delays or issues before customers call to ask.

**Automatic Notifications**: Set up ConnectWise workflows to notify customers of status changes.

**Improved Accuracy**: Eliminate manual data entry errors and ensure information consistency.

![Order Status Tracking Process](/public/assets/images/cw-purchase-order-tracking.webp)

## How Order Status Tracking Works

### Automatic Monitoring Process

The Get Order Status template continuously monitors your TD SYNNEX orders:

1. **Identify Orders to Track**: Finds purchase orders marked with "Send to TDS" = true
2. **Query TD SYNNEX**: Checks current status for each tracked order
3. **Compare Status**: Determines if any status changes have occurred
4. **Update ConnectWise**: Updates purchase orders with new status information
5. **Add Details**: Includes tracking numbers, shipping dates, and other relevant information
6. **Log Activity**: Records all status changes for audit and troubleshooting

### Order Status Lifecycle

Your orders progress through these status stages:

**Send to TDS**: Order is marked for submission to TD SYNNEX
**TDS Accepted**: TD SYNNEX has received and accepted the order
**TDS Released**: Order has been released for fulfillment processing
**TDS Shipped**: Order has been shipped with tracking information
**TDS Invoiced**: Order has been invoiced and billing is complete
**TDS Closed**: Order is complete and closed

### Information That Gets Updated

For each status change, the template updates:

**Order Status**: Current stage in the fulfillment process
**Tracking Numbers**: Shipping carrier tracking information
**Ship Dates**: When the order was shipped
**Delivery Dates**: Expected or actual delivery dates
**Invoice Information**: Invoice numbers and dates
**Carrier Details**: Shipping method and carrier information
**Special Notes**: Any special handling or delivery instructions

## Setting Up Order Status Tracking

### Prerequisites

Before enabling this template:
- **Create Orders template active**: Orders must be submitted through the integration
- **Proper order marking**: Orders must have "Send to TDS" field set to true
- **TD SYNNEX order numbers**: Orders must have valid TD SYNNEX order numbers
- **API connectivity**: Stable connection to TD SYNNEX systems

### Enabling the Template

1. **Access Integration Templates**
   - Go to your ConnectWise PSA connector in Digital Bridge
   - Click on the "Integration Templates" tab

2. **Enable Order Status Tracking**
   - Find "Get Order Status"
   - Toggle the switch to "Active"
   - Review the activation details panel

3. **Confirm Integration Settings**
   - Agree to enable TD SYNNEX order integration
   - Allow automatic order data transmission
   - Confirm that order tracking should begin immediately

### Configuring Order Tracking

**Automatic Tracking**: Orders submitted through the Create Orders template are automatically tracked.

**Manual Tracking**: For orders submitted outside the integration:
1. Open the purchase order in ConnectWise
2. Set "Send to TDS" field to "true"
3. Enter the TD SYNNEX order number in the "Vendor Order Number" field
4. Save the purchase order

**Tracking Frequency**: The template checks for status updates regularly throughout the day.

## Understanding Order Status Updates

### Status Progression

**TDS Accepted**
- TD SYNNEX has received your order
- Order details have been validated
- Order is queued for processing
- Estimated ship date may be provided

**TDS Released**
- Order has been released to the fulfillment center
- Products are being picked and packed
- Shipping arrangements are being made
- Ship date is confirmed

**TDS Shipped**
- Order has been shipped to the customer
- Tracking number is available
- Carrier and shipping method are confirmed
- Estimated delivery date is provided

**TDS Invoiced**
- Order has been invoiced
- Invoice number and date are recorded
- Billing process is complete
- Payment terms are in effect

**TDS Closed**
- Order fulfillment is complete
- All items have been delivered
- Any returns or issues have been resolved
- Order is archived

### Detailed Status Information

For each status update, you'll see:

**Timestamps**: Exact date and time of each status change
**Tracking Details**: Carrier, tracking number, and shipping method
**Delivery Information**: Expected delivery dates and special instructions
**Invoice Data**: Invoice numbers, dates, and amounts
**Line Item Status**: Individual product status for partial shipments
**Notes and Comments**: Any special handling or delivery notes

### Handling Partial Shipments

When orders ship in multiple parts:
- Each shipment gets its own tracking number
- Line items show individual shipping status
- Multiple "TDS Shipped" updates may occur
- Final "TDS Closed" happens when all items are delivered

## Using Order Status Information

### Customer Service Applications

**Proactive Communication**: Contact customers before they call you
- Notify customers when orders ship
- Provide tracking numbers immediately
- Alert customers to any delays or issues
- Confirm delivery completion

**Instant Status Updates**: When customers call for updates
- Access current status immediately in ConnectWise
- Provide accurate tracking information
- Explain any delays or issues
- Set proper expectations for delivery

### Internal Operations

**Inventory Management**: Use status information for
- Planning future orders
- Managing customer expectations
- Coordinating with other vendors
- Tracking delivery performance

**Project Management**: Integrate order status with project timelines
- Update project schedules based on delivery dates
- Coordinate installation and deployment activities
- Manage customer project expectations
- Plan resource allocation

### Workflow Automation

**ConnectWise Workflows**: Set up automated workflows to
- Send customer notifications when orders ship
- Create service tickets for delivery coordination
- Update project status based on order progress
- Generate reports on order performance

**Email Notifications**: Automatically notify
- Customers when orders ship
- Sales teams when orders are delivered
- Project managers when delays occur
- Management when issues arise

## Advanced Features

### Custom Status Fields

**Additional Tracking Fields**: Add custom fields to capture
- Customer-specific delivery requirements
- Project codes and references
- Special handling instructions
- Internal notes and comments

**Integration with Other Systems**: Connect order status to
- Project management systems
- Customer portals
- Accounting systems
- Inventory management

### Reporting and Analytics

**Order Performance Metrics**: Track
- Average delivery times
- On-time delivery rates
- Order accuracy and completeness
- Customer satisfaction scores

**Trend Analysis**: Identify patterns in
- Seasonal delivery variations
- Carrier performance
- Product availability
- Customer ordering behavior

### Exception Handling

**Delayed Orders**: Automatic alerts for
- Orders that miss expected ship dates
- Deliveries that are significantly delayed
- Orders stuck in processing
- Carrier delivery issues

**Problem Resolution**: Streamlined processes for
- Contacting TD SYNNEX about issues
- Coordinating with carriers
- Managing customer expectations
- Escalating problems when needed

## Troubleshooting Common Issues

### Status Updates Not Appearing

**Problem**: Order status doesn't update in ConnectWise
**Common Causes**:
- "Send to TDS" field not set to true
- Missing or incorrect TD SYNNEX order number
- API connectivity issues
- Order not found in TD SYNNEX systems

**Solutions**:
- Verify the "Send to TDS" field is set correctly
- Check that the TD SYNNEX order number is accurate
- Review the activity log for error messages
- Contact support if connectivity issues persist

### Incorrect Status Information

**Problem**: Status information appears wrong or outdated
**Common Causes**:
- Delays in TD SYNNEX system updates
- Multiple orders with similar numbers
- Data synchronization issues

**Solutions**:
- Verify order numbers match between systems
- Check TD SYNNEX directly for comparison
- Wait for the next update cycle
- Contact support for data reconciliation

### Missing Tracking Information

**Problem**: Order shows as shipped but no tracking number
**Common Causes**:
- Carrier hasn't provided tracking yet
- Special shipping arrangements
- International shipments with different tracking

**Solutions**:
- Wait for carrier to update tracking information
- Check with TD SYNNEX for special shipments
- Contact the carrier directly if needed
- Update customers about tracking delays

### Performance Issues

**Problem**: Status updates are slow or delayed
**Common Causes**:
- High order volume
- TD SYNNEX system performance
- Network connectivity issues

**Solutions**:
- Monitor the activity log for processing times
- Check network connectivity
- Contact support for performance optimization
- Consider adjusting update frequency if needed

## Best Practices

### Order Management

**Consistent Marking**: Always set "Send to TDS" to true for orders you want tracked.

**Accurate Information**: Ensure TD SYNNEX order numbers are correct and complete.

**Regular Monitoring**: Check the activity log regularly for any issues or errors.

**Customer Communication**: Use status information to keep customers informed proactively.

### Process Optimization

**Workflow Integration**: Set up ConnectWise workflows to automate customer notifications.

**Exception Handling**: Develop procedures for handling delayed or problematic orders.

**Performance Monitoring**: Track delivery performance and identify improvement opportunities.

**Team Training**: Ensure all team members understand how to use status information effectively.

### Customer Service Excellence

**Proactive Updates**: Contact customers with shipping and delivery information before they ask.

**Accurate Information**: Always provide current, accurate status information.

**Issue Resolution**: Address delivery problems quickly and professionally.

**Follow-up**: Confirm delivery completion and customer satisfaction.

## Integration with Other Templates

### Create Orders Dependency

Order Status tracking works best with Create Orders because:
- Orders are automatically marked for tracking
- TD SYNNEX order numbers are populated correctly
- The complete workflow is seamless from quote to delivery

### Product Sync Integration

Product information from Product Sync enhances status tracking:
- Product descriptions help identify specific items
- Category information aids in delivery planning
- Vendor details support customer communication

### Price & Availability Coordination

Status tracking complements pricing information:
- Delivery performance affects future pricing negotiations
- Availability patterns help with inventory planning
- Customer satisfaction impacts pricing discussions

## Performance Monitoring

### Key Metrics

**Update Frequency**: How often status information is refreshed
**Accuracy Rate**: Percentage of status updates that are correct
**Response Time**: How quickly status changes appear in ConnectWise
**Error Rate**: Percentage of orders that have tracking issues

### Regular Reviews

**Daily Monitoring**: Check for any orders with status issues
**Weekly Analysis**: Review delivery performance and customer feedback
**Monthly Reports**: Comprehensive analysis of order tracking effectiveness
**Quarterly Assessment**: Strategic review of process improvements

## Next Steps

With automated order status tracking working effectively:

1. **Set Up Customer Notifications**: Use ConnectWise workflows to automatically notify customers
2. **Train Your Team**: Ensure everyone knows how to use status information for customer service
3. **Monitor Performance**: Track delivery times and customer satisfaction
4. **Optimize Processes**: Refine your procedures based on experience
5. **Expand Integration**: Consider integrating with other business systems

Automated order status tracking completes your end-to-end TD SYNNEX integration, providing visibility and control throughout the entire order lifecycle. Use this capability to deliver exceptional customer service and operational efficiency.

