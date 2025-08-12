# Create Orders Template

## Overview

The Create Orders template automates the process of converting your ConnectWise sales orders into TD SYNNEX purchase orders. When you mark an opportunity as "Won" and create a sales order, this template handles the submission to TD SYNNEX automatically.

This eliminates the manual process of re-entering order information into TD SYNNEX systems, reduces errors, and speeds up order processing. Your sales orders become TD SYNNEX purchase orders without any additional work from your team.

## Why Automate Order Creation

### The Manual Process Problems

**Double Data Entry**: Without automation, you have to enter the same order information twice - once in ConnectWise and again in TD SYNNEX systems.

**Transcription Errors**: Manual re-entry leads to mistakes in product codes, quantities, shipping addresses, and other critical information.

**Time Delays**: Manual processing can add hours or days to order submission, delaying delivery to your customers.

**Inconsistent Information**: Different people may enter information differently, leading to inconsistencies between systems.

**Missed Orders**: Orders can fall through the cracks when relying on manual processes.

### Benefits of Automated Order Creation

**Faster Processing**: Orders are submitted to TD SYNNEX within 30 minutes of being marked for submission.

**Error Reduction**: Automated submission eliminates transcription errors and ensures data consistency.

**Complete Audit Trail**: Every order submission is logged with timestamps and status information.

**Automatic Updates**: ConnectWise purchase orders are updated with TD SYNNEX order numbers and status.

**Improved Customer Service**: Faster order processing means quicker delivery to your customers.

![Purchase Order Creation Process](/public/assets/images/cw-purchase-order-creation.webp)

## How the Template Works

### Automated Order Processing

The Create Orders template runs automatically every 30 minutes and follows this process:

1. **Scan for New Orders**: Looks for sales orders marked "Send to TDS"
2. **Validate Order Information**: Checks that all required information is present and correct
3. **Submit to TD SYNNEX**: Sends the order to TD SYNNEX via secure API
4. **Receive Confirmation**: Gets order number and acknowledgment from TD SYNNEX
5. **Update ConnectWise**: Updates the purchase order with TD SYNNEX information
6. **Log Results**: Records the submission results for your review

### Order Validation Process

Before submitting orders, the template validates:

**Product Information**:
- All products are valid TD SYNNEX SKUs
- Product quantities are within acceptable limits
- Products are currently available from TD SYNNEX

**Customer Information**:
- Shipping address is complete and valid
- Billing information is accurate
- Customer purchase order number (if required)

**Order Details**:
- All required fields are populated
- Order totals are reasonable
- Special instructions are included

## Setting Up Order Creation

### Prerequisites

Before enabling this template:
- **Product Sync must be active**: Orders can only include synced TD SYNNEX products
- **Price & Availability recommended**: Ensures current pricing and availability
- **Proper shipping setup**: Customer shipping addresses must be complete
- **TD SYNNEX vendor configured**: The TD SYNNEX vendor must be set up correctly

### Enabling the Template

1. **Access Integration Templates**
   - Go to your ConnectWise PSA connector in Digital Bridge
   - Click on the "Integration Templates" tab

2. **Enable Create Orders**
   - Find "Create Orders from ConnectWise"
   - Toggle the switch to "Active"
   - The template starts monitoring immediately

3. **No Additional Configuration**
   - The template works automatically once enabled
   - Runs every 30 minutes
   - No schedules or settings to configure

### Preparing Your Sales Orders

**Complete Product Information**:
- Use only TD SYNNEX products (synced products)
- Verify product codes and descriptions
- Ensure quantities are accurate

**Customer Details**:
- Complete shipping address with contact information
- Accurate billing address
- Customer purchase order number (if applicable)

**Order Status**:
- Set the purchase order status to "Send to TDS"
- This tells the template to process this order

## Using the Create Orders Template

### Standard Order Process

**Step 1: Create Opportunity**
- Create an opportunity with TD SYNNEX products
- Use real-time pricing to ensure current costs
- Complete all customer and product information

**Step 2: Mark Opportunity Won**
- When you win the deal, mark the opportunity as "Won"
- ConnectWise will create a sales order automatically
- Review the sales order for accuracy

**Step 3: Prepare Purchase Order**
- ConnectWise creates a purchase order from the sales order
- Verify all information is correct
- Set the vendor to "TD SYNNEX"
- Set the status to "Send to TDS"

**Step 4: Automatic Processing**
- The template will find your order within 30 minutes
- Order is validated and submitted to TD SYNNEX
- ConnectWise is updated with TD SYNNEX order information

**Step 5: Monitor Results**
- Check the purchase order for TD SYNNEX order number
- Review the activity log for any issues
- Follow up on any failed orders

### Order Status Updates

After submission, your ConnectWise purchase order is updated with:

**TD SYNNEX Order Number**: The official TD SYNNEX order number for tracking and reference.

**Order Acknowledgment**: Confirmation that TD SYNNEX has received and accepted the order.

**Estimated Ship Date**: When TD SYNNEX expects to ship the order.

**Order Status**: Current status in the TD SYNNEX fulfillment process.

**Error Messages**: Any issues that prevented successful submission.

## Managing Order Submissions

### Monitoring Order Activity

**Activity Log**: Check the activity log regularly to see:
- Which orders have been submitted successfully
- Any orders that failed submission
- Processing times and performance metrics
- Error messages and resolution steps

**Purchase Order Updates**: Monitor your purchase orders for:
- TD SYNNEX order numbers
- Status changes
- Error notifications
- Shipping updates

### Handling Failed Orders

**Common Failure Reasons**:
- Missing or invalid shipping information
- Products not available from TD SYNNEX
- Incomplete customer information
- API connectivity issues

**Resolution Steps**:
1. Review the error message in the activity log
2. Correct the issue in ConnectWise
3. Set the status back to "Send to TDS"
4. The template will retry on the next cycle

### Order Tracking and Follow-up

**TD SYNNEX Order Numbers**: Use these for:
- Tracking order status in TD SYNNEX systems
- Customer service inquiries
- Shipping and delivery coordination
- Invoice reconciliation

**Customer Communication**: Keep customers informed with:
- Order confirmation with TD SYNNEX order number
- Estimated delivery dates
- Tracking information when available
- Any delays or issues

## Advanced Configuration

### Custom Fields and Workflows

**Custom Order Fields**: You can add custom fields to capture:
- Special shipping instructions
- Customer purchase order numbers
- Project codes or references
- Billing requirements

**ConnectWise Workflows**: Set up workflows to:
- Automatically set orders to "Send to TDS" when appropriate
- Send notifications when orders are submitted
- Alert managers to failed orders
- Update customer records with order information

### Integration with Other Systems

**Accounting Integration**: Coordinate with your accounting system:
- Match TD SYNNEX invoices to ConnectWise orders
- Track costs and margins accurately
- Automate accounts payable processes

**Customer Portals**: Provide customers with:
- Order status updates
- Tracking information
- Delivery confirmations
- Invoice details

### Bulk Order Processing

For high-volume operations:
- The template can handle multiple orders simultaneously
- Large orders are processed efficiently
- Batch processing reduces API overhead
- Error handling ensures no orders are lost

## Troubleshooting Common Issues

### Order Submission Failures

**Problem**: Orders fail to submit to TD SYNNEX
**Common Causes**:
- Incomplete shipping addresses
- Invalid product codes
- Network connectivity issues
- TD SYNNEX system maintenance

**Solutions**:
- Verify all required fields are complete
- Check that products are valid TD SYNNEX SKUs
- Review error messages in the activity log
- Contact support for persistent issues

### Missing Order Numbers

**Problem**: Orders submit but don't get TD SYNNEX order numbers
**Common Causes**:
- API response delays
- ConnectWise update failures
- Partial order acceptance

**Solutions**:
- Check the activity log for submission details
- Verify the order in TD SYNNEX systems
- Contact support to retrieve missing order numbers

### Duplicate Orders

**Problem**: Same order appears to be submitted multiple times
**Common Causes**:
- Status field reset incorrectly
- Manual resubmission
- System errors

**Solutions**:
- Check TD SYNNEX for duplicate orders
- Review order status history
- Implement controls to prevent duplicate submissions

### Performance Issues

**Problem**: Orders take too long to process
**Common Causes**:
- High order volume
- Large orders with many line items
- API rate limiting

**Solutions**:
- Monitor processing times in the activity log
- Consider staggering large orders
- Contact support for performance optimization

## Best Practices

### Order Preparation

**Complete Information**: Ensure all order information is complete before marking for submission.

**Product Verification**: Verify all products are current TD SYNNEX SKUs with accurate pricing.

**Customer Details**: Double-check shipping and billing addresses for accuracy.

**Special Instructions**: Include any special shipping or handling requirements.

### Process Management

**Regular Monitoring**: Check the activity log daily for failed orders or issues.

**Error Resolution**: Address failed orders promptly to avoid customer delays.

**Status Tracking**: Monitor order status changes and communicate with customers.

**Performance Review**: Regularly review processing times and success rates.

### Team Training

**Order Entry Standards**: Train staff on proper order entry procedures.

**Error Handling**: Teach team members how to identify and resolve common issues.

**Customer Communication**: Establish procedures for updating customers on order status.

**Escalation Procedures**: Define when and how to escalate issues to management or support.

## Integration with Other Templates

### Product Sync Dependency

Create Orders requires Product Sync because:
- Only synced products can be submitted to TD SYNNEX
- Product mapping ensures accurate order submission
- Synced products have the necessary TD SYNNEX identifiers

### Price & Availability Integration

Using Price & Availability with Create Orders:
- Ensures orders are submitted with current pricing
- Verifies product availability before submission
- Reduces order failures due to pricing or stock issues

### Order Status Integration

Create Orders works seamlessly with Get Order Status:
- Submitted orders are automatically tracked
- Status updates flow back to ConnectWise
- Complete order lifecycle management

## Performance Metrics

### Key Performance Indicators

**Order Success Rate**: Percentage of orders successfully submitted on first attempt.

**Processing Time**: Average time from order creation to TD SYNNEX submission.

**Error Rate**: Percentage of orders that fail submission and require manual intervention.

**Customer Satisfaction**: Impact on delivery times and customer experience.

### Monitoring and Reporting

**Daily Metrics**: Track daily order volume and success rates.

**Weekly Reviews**: Analyze trends and identify improvement opportunities.

**Monthly Reports**: Comprehensive analysis of order processing performance.

**Quarterly Assessments**: Strategic review of automation benefits and ROI.

## Next Steps

With automated order creation working effectively:

1. **Enable Order Status Tracking**: Complete the automation with status updates
2. **Train Your Team**: Ensure everyone understands the new automated process
3. **Monitor Performance**: Track success rates and processing times
4. **Optimize Workflows**: Refine your processes based on experience
5. **Expand Usage**: Apply automation to more of your TD SYNNEX business

Automated order creation is a game-changer for efficiency and accuracy. Use this capability to streamline your operations and improve customer satisfaction.

