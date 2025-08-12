# Get Order Status Template

## What This Template Does

The Get Order Status template monitors your TD SYNNEX orders and automatically updates the corresponding Autotask purchase orders with current status, tracking information, and delivery details.

This template provides real-time visibility into your TD SYNNEX orders without requiring you to check multiple systems. All order status information appears directly in your Autotask purchase orders.

![Autotask Purchase Order List with Status](/public/assets/images/autotask-purchase-order-list.png)

### Key Features

**Automatic Status Updates**: Continuously monitors TD SYNNEX orders and updates Autotask with current status.

**Tracking Information**: Adds shipping tracking numbers and carrier details to purchase orders.

**Delivery Updates**: Updates expected and actual delivery dates.

**Invoice Details**: Includes TD SYNNEX invoice numbers and amounts when available.

**Multi-Status Support**: Handles all order states from processing through delivery.

## Prerequisites

**Submit Order Required**: The Submit Order template must be enabled to create orders that can be tracked.

**API Permissions**: Your Autotask API user needs update access to Purchase Orders and Purchase Order Line Items.

**Active Orders**: You must have orders submitted to TD SYNNEX to track.

## How Order Status Tracking Works

### Status Monitoring Process

1. **Order Identification**: The template identifies Autotask purchase orders that were submitted to TD SYNNEX
2. **Status Checking**: Regularly queries TD SYNNEX for current order status
3. **Data Comparison**: Compares current status with last known status in Autotask
4. **Update Application**: Updates Autotask purchase orders with new status information
5. **Notification**: Logs all status changes for review and reporting

### Order Status Lifecycle

**New**: Order has been created in Autotask but not yet submitted to TD SYNNEX.

**Submitted**: Order has been sent to TD SYNNEX and is awaiting processing.

**Received**: TD SYNNEX has received and acknowledged the order.

**Processing**: Order is being prepared for shipment.

**Shipped**: Order has been shipped with tracking information.

**Delivered**: Order has been delivered to the specified address.

**Invoiced**: TD SYNNEX has generated an invoice for the order.

**Closed**: Order is complete and closed.

### Information Updated

**Order Status**: Current processing state of the order.

**Tracking Numbers**: Shipping carrier tracking numbers for packages.

**Carrier Information**: Shipping carrier name and service level.

**Expected Delivery**: Estimated delivery date from carrier.

**Actual Delivery**: Confirmed delivery date and time.

**Invoice Details**: TD SYNNEX invoice number and amount.

**Line Item Status**: Individual product status within the order.

## Configuration Steps

### Step 1: Enable Order Status Tracking

1. **Navigate to Integration Templates**
   - Go to your Autotask connector in Digital Bridge
   - Click the **Integration Templates** tab

2. **Configure Get Order Status**
   - Find the **Get Order Status** template tile
   - Click **Change Settings** if configuration options are available
   - Use the toggle to turn the template **On**

### Step 2: Set Monitoring Options

**Update Frequency**:
- **Real-time**: Checks for status updates continuously
- **Hourly**: Updates status every hour
- **Daily**: Updates status once per day
- **Custom**: Set specific update intervals

**Status Scope**:
- **All Orders**: Monitors all TD SYNNEX orders
- **Recent Orders**: Only tracks orders from the last 30/60/90 days
- **Active Orders**: Only monitors orders that are not yet delivered

**Notification Settings**:
- **Status Change Alerts**: Notifications when order status changes
- **Delivery Notifications**: Alerts when orders are delivered
- **Error Notifications**: Alerts for tracking issues

## Understanding Status Updates in Autotask

### Where Status Appears

**Purchase Order Header**: Overall order status and tracking information.

**Line Item Details**: Individual product status and tracking.

**Order Notes**: Detailed status history and updates.

**Custom Fields**: Additional TD SYNNEX-specific information.

### Status Information Fields

**Order Level**:
- TD SYNNEX order number
- Current order status
- Expected delivery date
- Total order value
- Invoice information

**Line Item Level**:
- Individual product status
- Quantity shipped vs. ordered
- Tracking numbers for each shipment
- Delivery confirmation details

**Tracking Details**:
- Carrier name and service
- Tracking number links
- Shipment weight and dimensions
- Delivery address confirmation

## Monitoring Order Status

### Sync Activity Log

The Sync Activity Log shows:
- Orders being monitored
- Status updates applied
- Any errors or issues
- Performance metrics

### Status Update History

**Change Tracking**: Complete history of all status changes.

**Timestamp Records**: When each update occurred.

**Source Information**: Whether updates came from TD SYNNEX or carrier.

**User Notifications**: Who was notified of status changes.

## Using Status Information

### Customer Communication

**Proactive Updates**: Use status information to update customers before they ask.

**Accurate Information**: Provide real-time delivery estimates and tracking numbers.

**Issue Resolution**: Quickly identify and address delivery problems.

**Professional Service**: Demonstrate proactive order management.

### Internal Operations

**Inventory Planning**: Use delivery information for inventory management.

**Project Scheduling**: Plan installations and deployments based on delivery dates.

**Resource Allocation**: Assign staff based on expected deliveries.

**Performance Monitoring**: Track TD SYNNEX delivery performance.

## Troubleshooting Order Status

### Common Issues

**Status Not Updating**:
- Verify the order was submitted through the Submit Order template
- Check that the TD SYNNEX order number is recorded correctly
- Ensure API user has update permissions for purchase orders

**Missing Tracking Information**:
- Confirm the order has actually shipped
- Check that TD SYNNEX has provided tracking details
- Verify carrier integration is working properly

**Incorrect Status**:
- Review the order details in both systems
- Check for manual changes that might conflict
- Verify the order number mapping is correct

### Performance Optimization

**Update Frequency**: Balance real-time updates with system performance.

**Order Scope**: Limit monitoring to active orders to improve performance.

**Error Handling**: Configure appropriate retry and error handling settings.

**Logging Level**: Adjust logging detail based on troubleshooting needs.

## Best Practices

### Setup and Configuration

**Start Simple**: Begin with basic status tracking and add features gradually.

**Test Thoroughly**: Verify status updates work correctly with test orders.

**Monitor Performance**: Watch system performance and adjust settings as needed.

**Document Process**: Keep records of configuration choices and changes.

### Ongoing Management

**Regular Review**: Check status update accuracy periodically.

**Customer Training**: Train customer service staff on using status information.

**Process Integration**: Incorporate status updates into your standard workflows.

**Performance Monitoring**: Track delivery performance and identify trends.

### Data Management

**Archive Old Orders**: Remove tracking for very old completed orders.

**Clean Up Data**: Periodically review and clean up status information.

**Backup Important Data**: Maintain backups of critical order information.

**Audit Trail**: Keep records of all status changes for accountability.

## Integration Benefits

### Operational Efficiency

**Reduced Manual Work**: Eliminates need to manually check order status.

**Faster Response**: Quickly answer customer questions about orders.

**Proactive Management**: Identify and address issues before they become problems.

**Better Planning**: Use delivery information for better resource planning.

### Customer Service

**Real-time Information**: Provide customers with current, accurate status.

**Professional Image**: Demonstrate sophisticated order management capabilities.

**Problem Resolution**: Quickly identify and resolve delivery issues.

**Communication**: Keep customers informed throughout the order process.

## Next Steps

### After Order Status is Working

1. **Train Your Team**: Show staff how to use status information effectively
2. **Develop Processes**: Create standard procedures for using status updates
3. **Customer Communication**: Establish customer notification procedures
4. **Performance Monitoring**: Track and optimize delivery performance

### Continuous Improvement

**Feedback Collection**: Gather feedback from staff and customers on status information.

**Process Refinement**: Continuously improve how you use status data.

**System Integration**: Integrate status information with other business systems.

**Performance Analysis**: Use status data to analyze and improve operations.

The Get Order Status template provides complete visibility into your TD SYNNEX orders, enabling better customer service and more efficient operations through real-time order tracking in Autotask PSA.

