---
title: Returns
category: Returns_Management
api_name: Returns
method: GET
path: /v3/returns
---

**Category:** Returns_Management
**API:** Returns

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/returns

## API Description
Returns

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| returnOrderId (query) | string | No | Return order identifier of the return order object as part of array. This is the same as RMA number. |
| customerOrderId (query) | string | No | A unique ID associated with the sales order for specified customer |
| status (query) | string | No | Status may be specified to query the returns with specific status.Valid statuses are: INITIATED, DELIVERED, COMPLETED |
| replacementInfo (query) | string | No | Provides additional attributes - replacementCustomerOrderID, returnType, rechargeReason, returnCancellationReason - related to Replacement return order, in response, if available. Allowed values are true or false. |
| returnType (query) | string | No | Specifies if the return order is a replacement return or a regular (refund) return. Possible values are REPLACEMENT or REFUND. |
| returnCreationStartDate (query) | date-time | No | Start Date for querying all return orders that were created after that date. Use one of the following formats, based on UTC, ISO 8601. Date example: '2013-08-16' Timestamp example: '2013-08-16T10:30:15Z' |
| returnCreationEndDate (query) | date-time | No | Limits the query to the return orders that were created before this returnCreationEndDate. Use one of the following formats, based on ISO 8601, are allowed: UTC date or timestamp. Examples: '2016-08-16T10:30:30.155Z' or '2016-08-16' |
| returnLastModifiedStartDate (query) | date-time | No | Start Date for querying all return orders that were modified after that date. Use one of the following formats, based on UTC, ISO 8601. Date example: '2013-08-16' Timestamp example: '2013-08-16T10:30:15Z'.In case of dates with timezone, use format '2020-04-17T10:42:41.000+0000' and follow encode '+' |
| returnLastModifiedEndDate (query) | date-time | No | Limits the query to the return orders that were modified before this date. Use one of the following formats, based on UTC, ISO 8601. Date example: '2013-08-16' Timestamp example: '2013-08-18T10:30:15Z'.In case of dates with timezone, use format '2020-04-18T10:42:41.000+0000' and follow encode '+' wi |
| limit (query) | string | No | The number of orders to be returned. Cannot be larger than 200 |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| meta | object | Yes |  |
| meta.totalCount | integer | No |  |
| meta.limit | integer | No |  |
| meta.nextCursor | string | No |  |
| returnOrders | array<object> | Yes | List of returns for the seller. |
| returnOrders.returnOrderId | string | No | Return order identifier of the return order. This is the same as RMA number. |
| returnOrders.customerEmailId | string | No | Customer email address |
| returnOrders.returnType | string | No | Specifies if the return order is a replacement return or a regular (refund) return. Possible values are REPLACEMENT or REFUND. |
| returnOrders.replacementCustomerOrderId | string | No | customer order ID of the original return order on which the replacement is created. |
| returnOrders.customerName | object | No | Customer information |
| returnOrders.customerName.firstName | string | No | Customer first name |
| returnOrders.customerName.lastName | string | No | Customer last name |
| returnOrders.customerOrderId | string | No | A unique ID associated with the sales order for specified customer |
| returnOrders.returnOrderDate | date-time | No | Date format for return order date |
| returnOrders.returnByDate | date-time | No | Date format for return by order date |
| returnOrders.refundMode | string | No | Determines when the refund was/will be issued to the customer |
| returnOrders.totalRefundAmount | object | No | Price of One unit of item, in this order line |
| returnOrders.totalRefundAmount.currencyAmount | number | No | Amount to be refunded. It can be upto two decimal points. |
| returnOrders.totalRefundAmount.currencyUnit | string | No | Currency information |
| returnOrders.returnLineGroups | array<object> | No | These groups are created per label or type of carrier service required. (e.g., If order has some lines that can be clubbed and mailed together as a smart post then they belong to one return group. If a line is bulky and needs a different type of carrier service, then that line will be part of differ |
| returnOrders.returnLineGroups.groupNo | integer | No | Sequence of group numbers where each returnLineGroups will represent one or more return lines |
| returnOrders.returnLineGroups.returnLines | array<object> | No | Array of return lines |
| returnOrders.returnLineGroups.returnLines.returnOrderLineNumber | integer | No | Identifier of the return label |
| returnOrders.returnLineGroups.labels | array<object> | No | Array of labels |
| returnOrders.returnLineGroups.labels.labelImageURL | string | No | Url to get the return label |
| returnOrders.returnLineGroups.labels.carrierInfoList | array<object> | No | Carrier information for the return |
| returnOrders.returnLineGroups.labels.carrierInfoList.carrierId | string | No | ID of the carrier used for the return |
| returnOrders.returnLineGroups.labels.carrierInfoList.carrierName | string | No | Name of the carrier used |
| returnOrders.returnLineGroups.labels.carrierInfoList.serviceType | string | No | the type of service used |
| returnOrders.returnLineGroups.labels.carrierInfoList.trackingNo | string | No | Tracking number of the order |
| returnOrders.returnLineGroups.returnExpectedFlag | boolean | No | Is customer required to send this item back to return center |
| returnOrders.returnOrderLines | array<object> | No | A list of order lines in the return order |
| returnOrders.returnOrderLines.returnOrderLineNumber | integer | No | The returns order line number for that return |
| returnOrders.returnOrderLines.salesOrderLineNumber | integer | No | The sales order line number for the return created |
| returnOrders.returnOrderLines.sellerOrderId | string | No | A unique ID associated with the sales order for specified Seller; gives Sellers the ability to print their own custom order ID on the return label; limit of 30 characters |
| returnOrders.returnOrderLines.returnReason | string | No | Gives the reason that was selected during the return creation. Reason codes are: ARRIVED_LATE, AUTO_RETURN, BOUGHT_ANOTHER_SIZE_OR_COLOR, BOUGHT_SOMEWHERE_ELSE, DAMAGED, DEFECTIVE, DUPLICATE_ITEM, INADEQUATE_QUALITY, INCORRECT_ITEM, LOST_AFTER_DELIVERY, LOST_IN_TRANSIT, LOWER_PRICE, MISSING_PARTS, N |
| returnOrders.returnOrderLines.purchaseOrderId | string | No | The purchase order ID for the return created |
| returnOrders.returnOrderLines.purchaseOrderLineNumber | integer | No | The purchase order line number for the return created |
| returnOrders.returnOrderLines.exceptionItemType | string | No |  |
| returnOrders.returnOrderLines.isReturnForException | boolean | No |  |
| returnOrders.returnOrderLines.rechargeReason | string | No | reason for recharging the customer for replacement |
| returnOrders.returnOrderLines.returnCancellationReason | string | No | reason for cancelling the return |
| returnOrders.returnOrderLines.item | object | No | Details of the item to be returned |
| returnOrders.returnOrderLines.item.sku | string | No | An arbitrary alphanumeric unique ID, specified by the seller, which identifies each item. |
| returnOrders.returnOrderLines.item.productName | string | No | The name of the product associated with the line item. Example: 'Kenmore CF1' or '2086883 Canister Secondary Filter Generic 2 Pack' |
| returnOrders.returnOrderLines.item.itemWeight | object | No | Total quantity returned in this return line |
| returnOrders.returnOrderLines.item.itemWeight.unitOfMeasure | string | No | The unit of measure in the item's weight (e.g., 'POUND' or 'OUNCE') |
| returnOrders.returnOrderLines.item.itemWeight.measurementValue | number | No | The quantity of the unit of measure for the item |
| returnOrders.returnOrderLines.charges | array<object> | No | Information relating to the charge for the orderLine |
| returnOrders.returnOrderLines.charges.chargeCategory | string | No | The category type. (e.g., 'PRODUCT' or 'FEE') |
| returnOrders.returnOrderLines.charges.chargeName | string | No | If chargeType is PRODUCT, chargeName is Item Price. If chargeType is SHIPPING, chargeName is Shipping |
| returnOrders.returnOrderLines.charges.chargePerUnit | object | No | Price of One unit of item, in this order line |
| returnOrders.returnOrderLines.charges.chargePerUnit.currencyAmount | number | No | Amount to be refunded. It can be upto two decimal points. |
| returnOrders.returnOrderLines.charges.chargePerUnit.currencyUnit | string | No | Currency information |
| returnOrders.returnOrderLines.charges.isDiscount | boolean | No | Is this charge a discount, which then needs to be subtracted from the refund |
| returnOrders.returnOrderLines.charges.isBillable | boolean | No | Should this charge be included in the refund computation |
| returnOrders.returnOrderLines.charges.tax | array<object> | No | Taxes for each charge |
| returnOrders.returnOrderLines.charges.tax.taxName | string | No | Name of the tax |
| returnOrders.returnOrderLines.charges.tax.excessTax | object | No | Price of One unit of item, in this order line |
| returnOrders.returnOrderLines.charges.tax.excessTax.currencyAmount | number | No | Amount to be refunded. It can be upto two decimal points. |
| returnOrders.returnOrderLines.charges.tax.excessTax.currencyUnit | string | No | Currency information |
| returnOrders.returnOrderLines.charges.tax.taxPerUnit | object | No | Price of One unit of item, in this order line |
| returnOrders.returnOrderLines.charges.tax.taxPerUnit.currencyAmount | number | No | Amount to be refunded. It can be upto two decimal points. |
| returnOrders.returnOrderLines.charges.tax.taxPerUnit.currencyUnit | string | No | Currency information |
| returnOrders.returnOrderLines.charges.excessCharge | object | No | Price of One unit of item, in this order line |
| returnOrders.returnOrderLines.charges.excessCharge.currencyAmount | number | No | Amount to be refunded. It can be upto two decimal points. |
| returnOrders.returnOrderLines.charges.excessCharge.currencyUnit | string | No | Currency information |
| returnOrders.returnOrderLines.charges.references | array<object> | No | Used only for OG |
| returnOrders.returnOrderLines.charges.references.name | string | No |  |
| returnOrders.returnOrderLines.charges.references.value | string | No |  |
| returnOrders.returnOrderLines.unitPrice | object | No | Price of One unit of item, in this order line |
| returnOrders.returnOrderLines.unitPrice.currencyAmount | number | No | Amount to be refunded. It can be upto two decimal points. |
| returnOrders.returnOrderLines.unitPrice.currencyUnit | string | No | Currency information |
| returnOrders.returnOrderLines.itemReturnSettings | array<object> | No | Contains name value pairs of calculated charges for the line. Eg: if order line has 3 Qty, this will have a shipping charge = 3 * shipping charge per unit (This is present in the line level charges). |
| returnOrders.returnOrderLines.itemReturnSettings.name | string | No |  |
| returnOrders.returnOrderLines.itemReturnSettings.value | string | No |  |
| returnOrders.returnOrderLines.chargeTotals | array<object> | No | Contains name value pairs of calculated charges for the line. Eg: if order line has 3 Qty, this will have a shipping charge = 3 * shipping charge per unit (This is present in the line level charges). |
| returnOrders.returnOrderLines.chargeTotals.name | string | No | Charge Names: lineUnitPrice, lineProductTaxes, lineTotalTaxes, lineRestockingFee, lineShippingFee, lineSubTotal, lineTotal. |
| returnOrders.returnOrderLines.chargeTotals.value | object | No | Price of One unit of item, in this order line |
| returnOrders.returnOrderLines.chargeTotals.value.currencyAmount | number | No | Amount to be refunded. It can be upto two decimal points. |
| returnOrders.returnOrderLines.chargeTotals.value.currencyUnit | string | No | Currency information |
| returnOrders.returnOrderLines.cancellableQty | integer | No | How much quantity of this order line can be cancelled |
| returnOrders.returnOrderLines.quantity | object | No | Total quantity returned in this return line |
| returnOrders.returnOrderLines.quantity.unitOfMeasure | string | No | The unit of measure in the item's weight (e.g., 'POUND' or 'OUNCE') |
| returnOrders.returnOrderLines.quantity.measurementValue | number | No | The quantity of the unit of measure for the item |
| returnOrders.returnOrderLines.returnExpectedFlag | boolean | No | Is customer required to send this item back to return center. |
| returnOrders.returnOrderLines.isFastReplacement | boolean | No | Applicable only for 1P. |
| returnOrders.returnOrderLines.isKeepIt | boolean | No | Is customer allowed to keep the product and not required to send it back to return center. This flag is determined by making a call to fraud system. |
| returnOrders.returnOrderLines.lastItem | boolean | No | This return is the last item on the sales order line and all other sales order line items are already returned. Helps in last penny calculations. |
| returnOrders.returnOrderLines.refundedQty | number | No | The quantity for which customer was refunded |
| returnOrders.returnOrderLines.rechargeableQty | number | No | The quantity for which customer can be charged again for |
| returnOrders.returnOrderLines.refundChannel | string | No | Determines the mode of refund initiation. Valid values are: WALMART_SETTLED_REFUND, SELLER_AUTO_REFUND, SELLER_MANUAL_REFUND, SELLER_SYSTEM_REFUND, and WALMART_TRIGGERED_REFUND. |
| returnOrders.returnOrderLines.returnTrackingDetail | array<object> | No | Informational blocks added as the return order completes its journey from return creation to received and refunded. |
| returnOrders.returnOrderLines.returnTrackingDetail.sequenceNo | integer | No | The stage the return is in. (e.g., '1' is an initiated return) |
| returnOrders.returnOrderLines.returnTrackingDetail.eventTag | string | No | The last completed return event. (e.g., 'RETURN_IN_TRANSIT') |
| returnOrders.returnOrderLines.returnTrackingDetail.eventDescription | string | No | Description of current return status event. (e.g., 'A MARKET_PLACE Return in Transit') |
| returnOrders.returnOrderLines.returnTrackingDetail.eventTime | date-time | No | Timestamp of listed event |
| returnOrders.returnOrderLines.returnTrackingDetail.references | array<object> | No | Used only for 1P |
| returnOrders.returnOrderLines.returnTrackingDetail.references.name | string | No |  |
| returnOrders.returnOrderLines.returnTrackingDetail.references.value | string | No |  |
| returnOrders.returnOrderLines.status | string | No | Current status of return. (e.g., 'INITIATED') |
| returnOrders.returnOrderLines.statusTime | date-time | No | Timestamp of listed status change |
| returnOrders.returnOrderLines.currentDeliveryStatus | string | No | Determines the current carrier tracking status of the return. |
| returnOrders.returnOrderLines.currentRefundStatus | string | No | Determines the current refund status of the return. |
| returnOrders.returnChannel | object | No | The channel via order return got initiated |
| returnOrders.returnChannel.channelName | string | No | Valid values are: ONLINE, IN_STORE, and CUSTOMER_CARE |
