---
title: Cancel_Order_Lines
category: Order_Management
api_name: Cancel_Order_Lines
method: POST
path: /v3/orders/{purchaseOrderId}/cancel
---

**Category:** Order_Management
**API:** Cancel_Order_Lines

**Method:** POST
**HTTP Path:** https://marketplace.walmartapis.com/v3/orders/{purchaseOrderId}/cancel

## API Description
Cancel Order Lines

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| purchaseOrderId (path) | string | Yes | purchaseOrderId |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| orderCancellation | object | No | Container for the cancellation details |
| orderCancellation.orderLines | object | No | A list of orderLines to be cancelled |
| orderCancellation.orderLines.orderLine | array<object> | No | Information to update the orderLine with cancellation details |
| orderCancellation.orderLines.orderLine.lineNumber | string | No |  |
| orderCancellation.orderLines.orderLine.orderLineStatuses | object | No | A list of statuses which should contain the new cancellation status |
| orderCancellation.orderLines.orderLine.orderLineStatuses.orderLineStatus | array<object> | No | List of details about the cancellation status update |
| orderCancellation.orderLines.orderLine.orderLineStatuses.orderLineStatus.status | string | No | Use 'Cancelled' (Created, Acknowledged, Shipped, Delivered, Cancelled, Refund) |
| orderCancellation.orderLines.orderLine.orderLineStatuses.orderLineStatus.cancellationReason | string | No | Reason for cancellation. Example: 'CUSTOMER_REQUESTED_SELLER_TO_CANCEL'. Cancellation reason should not be "CUSTOMER_REQUESTED_SELLER_TO_CANCEL" for non intent to cancel orders' (CUSTOMER_REQUESTED_SELLER_TO_CANCEL, SELLER_CANCEL_PRICING_ERROR, SELLER_CANCEL_OUT_OF_STOCK, SELLER_CANCEL_FRAUD_STOP_SHIPMENT, SELLER_CANCEL_ADDRESS_NOT_SERVICEABLE) |
| orderCancellation.orderLines.orderLine.orderLineStatuses.orderLineStatus.statusQuantity | object | No | Details about the status update |
| orderCancellation.orderLines.orderLine.orderLineStatuses.orderLineStatus.statusQuantity.unitOfMeasurement | string | No | Unit of quantity (EACH, EA) |
| orderCancellation.orderLines.orderLine.orderLineStatuses.orderLineStatus.statusQuantity.amount | string | No | Always use '1' |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| order | object | No | Information about the purchase order |
| order.purchaseOrderId | string | No | A unique ID associated with the seller's purchase order |
| order.customerOrderId | string | No | A unique ID associated with the sales order for specified customer |
| order.customerEmailId | string | No | The email address of the customer for the sales order |
| order.orderType | string | No | Specifies if the order is a regular order or replacement order. Possible values are REGULAR or REPLACEMENT. Provided in response only if query parameter replacementInfo=true. |
| order.originalCustomerOrderID | string | No | customer order ID of the original customer order on which the replacement is created. |
| order.orderDate | integer | No | The date the customer submitted the sales order |
| order.buyerId | uuid | No | Unique ID associated with the specified buyer |
| order.mart | string | No | Mart information |
| order.isGuest | boolean | No | Indicates a guest customer |
| order.shippingInfo | object | No | The shipping information provided by the customer to the seller |
| order.shippingInfo.phone | string | No | The customer's phone number |
| order.shippingInfo.estimatedDeliveryDate | integer | No | The estimated time and date for the delivery of the item. Format: yyyy-MM-ddThh:MM:ssZ Example: '2020-06-15T06:00:00Z' |
| order.shippingInfo.estimatedShipDate | integer | No | The estimated time and date when the item will be shipped. Format: yyyy-MM-ddThh:MM:ssZ Example: '2020-06-15T06:00:00Z' |
| order.shippingInfo.methodCode | string | No | The shipping method. Can be one of the following: Standard, Express, OneDay, WhiteGlove, Value or Freight (Standard, Express, OneDay, Freight, WhiteGlove, Value) |
| order.shippingInfo.postalAddress | object | No | Elements of the customer's postal address |
| order.shippingInfo.postalAddress.name | string | No | The name for the person/place of shipping address |
| order.shippingInfo.postalAddress.address1 | string | No | The first line of the shipping address |
| order.shippingInfo.postalAddress.address2 | string | No | The second line of the shipping address |
| order.shippingInfo.postalAddress.city | string | No | The city of the shipping address |
| order.shippingInfo.postalAddress.state | string | No | The state of the shipping address |
| order.shippingInfo.postalAddress.postalCode | string | No | The zip code of the shipping address |
| order.shippingInfo.postalAddress.country | string | No | The country of the shipping address |
| order.shippingInfo.postalAddress.addressType | string | No | The address type, example: 'RESIDENTIAL' |
| order.orderLines | object | No | A list of order lines in the order |
| order.orderLines.orderLine | array<object> | No | A list of order lines in the order |
| order.orderLines.orderLine.lineNumber | string | No | The line number associated with the details for each individual item in the purchase order |
| order.orderLines.orderLine.item | object | No | The information for the item on the orderLine |
| order.orderLines.orderLine.item.productName | string | No | The name of the product associated with the line item. Example: 'Kenmore CF1' or '2086883 Canister Secondary Filter Generic 2 Pack' |
| order.orderLines.orderLine.item.sku | string | No | An arbitrary alphanumeric unique ID, assigned to each item in the item file |
| order.orderLines.orderLine.item.imageUrl | string | No | Optional. Web URL for the image of the item. |
| order.orderLines.orderLine.item.weight | object | No | Optional. Weight information for the item. |
| order.orderLines.orderLine.item.weight.value | string | No | Numerical amount of weight parameter. |
| order.orderLines.orderLine.item.weight.unit | string | No | Standard value of measurement of the item. Example: 'Pounds' |
| order.orderLines.orderLine.charges | object | No | Information relating to the charge for the orderLine |
| order.orderLines.orderLine.charges.charge | array<object> | No | Information relating to the charge for the orderLine |
| order.orderLines.orderLine.charges.charge.chargeType | string | No | The charge type for line items can be one of the following: PRODUCT or SHIPPING For details, refer to 'Charge Types' |
| order.orderLines.orderLine.charges.charge.chargeName | string | No | If chargeType is PRODUCT, chargeName is Item Price. If chargeType is SHIPPING, chargeName is Shipping |
| order.orderLines.orderLine.charges.charge.chargeAmount | object | No | The details for the amount of the tax charge |
| order.orderLines.orderLine.charges.charge.chargeAmount.currency | string | No | The type of currency for the charge. Example: USD for US Dollars (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| order.orderLines.orderLine.charges.charge.chargeAmount.amount | number | No | The numerical amount for that charge. Example: 9.99 |
| order.orderLines.orderLine.charges.charge.tax | object | No | Tax information for the charge, including taxName and taxAmount |
| order.orderLines.orderLine.charges.charge.tax.taxName | string | No | The name associated with the tax. Example: 'Sales Tax' |
| order.orderLines.orderLine.charges.charge.tax.taxAmount | object | No | The details for the amount of the tax charge |
| order.orderLines.orderLine.charges.charge.tax.taxAmount.currency | string | No | The type of currency for the charge. Example: USD for US Dollars (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| order.orderLines.orderLine.charges.charge.tax.taxAmount.amount | number | No | The numerical amount for that charge. Example: 9.99 |
| order.orderLines.orderLine.orderLineQuantity | object | No | Details about the status update |
| order.orderLines.orderLine.orderLineQuantity.unitOfMeasurement | string | No | Unit of quantity (EACH, EA) |
| order.orderLines.orderLine.orderLineQuantity.amount | string | No | Always use '1' |
| order.orderLines.orderLine.statusDate | integer | No | The date shown on the recent order status |
| order.orderLines.orderLine.orderLineStatuses | object | No | A list of statuses for the Order Line |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus | array<object> | No | Detail List of Order Line status |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.status | string | No | Should be 'Created' (Created, Acknowledged, Shipped, Delivered, Cancelled, Refund) |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.statusQuantity | object | No | Details about the status update |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.statusQuantity.unitOfMeasurement | string | No | Unit of quantity (EACH, EA) |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.statusQuantity.amount | string | No | Always use '1' |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.cancellationReason | string | No | If order is cancelled, cancellationReason will explain the reason |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo | object | No | List of information about the package shipment and tracking updates |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.shipDateTime | integer | No | The date the package was shipped |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.carrierName | object | No | Information about the package carrier(s) |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.carrierName.otherCarrier | string | No | Other carrier name, When otherCarrier is used, trackingUrl must also be provided |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.carrierName.carrier | string | No | The package shipment carrier. Valid entries are: UPS, USPS, FedEx, Airborne, OnTrac, DHL Ecommerce - US, LS (LaserShip), UDS (United Delivery Service), UPSMI (UPS Mail Innovations), FDX, PILOT, ESTES, SAIA, FDS Express, Seko Worldwide, HIT Delivery, FEDEXSP (FedEx SmartPost), RL Carriers, Metropolit (UPS, USPS, FedEx, Airborne, OnTrac, DHL Ecommerce - US, LS, UDS, UPSMI, FDX, PILOT, ESTES, SAIA, FDS Express, Seko Worldwide, HIT Delivery, FEDEXSP, RL Carriers, Metropolitan Warehouse & Delivery, China Post, YunExpress, Yellow Freight Sys, AIT Worldwide Logistics, Chukou1, Sendle, Landmark Global, Sunyou, Yanwen, 4PX, GLS, OSM Worldwide, FIRST MILE, AM Trucking, CEVA, India Post, SF Express, CNE, TForce Freight, AxleHire, LSO) |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.methodCode | string | No | The shipping method. Can be one of the following: Standard, Express, OneDay, WhiteGlove, Value or Freight (Standard, Express, OneDay, Freight, WhiteGlove, Value) |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.trackingNumber | string | No | The shipment tracking number |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.trackingURL | string | No | The URL for tracking the shipment. This parameter is mandatory if the otherCarrier parameter is used |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress | object | No | Gives Sellers the ability to specify the RC center address during fulfillment; any returns created for the PO will always be returned to the RC address specified |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.name | string | No | The name for the person/place of return address |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.address1 | string | No | The first line of the return address |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.address2 | string | No | The second line of the return address |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.city | string | No | The city of the return address |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.state | string | No | The state of the return address |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.postalCode | string | No | The zip code of the return address |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.country | string | No | The country of the return address |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.dayPhone | string | No | Phone of the center where the package shipment is returned |
| order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.emailId | string | No | Email of the center where the package shipment is returned |
| order.orderLines.orderLine.returnOrderId | string | No | Id of the return order created in case of a full refund |
| order.orderLines.orderLine.refund | object | No | Details about any partial refund on the order |
| order.orderLines.orderLine.refund.refundId | string | No |  |
| order.orderLines.orderLine.refund.refundComments | string | No |  |
| order.orderLines.orderLine.refund.refundCharges | object | No |  |
| order.orderLines.orderLine.refund.refundCharges.refundCharge | array<object> | No |  |
| order.orderLines.orderLine.refund.refundCharges.refundCharge.refundReason | string | No |  (BillingError, TaxExemptCustomer, ItemNotAsAdvertised, IncorrectItemReceived, CancelledYetShipped, ItemNotReceivedByCustomer, IncorrectShippingPrice, DamagedItem, DefectiveItem, CustomerChangedMind, CustomerReceivedItemLate, Missing Parts / Instructions, Finance -> Goodwill, Finance -> Rollback, Buyer canceled, Customer returned item, General adjustment, Merchandise not received, Quality -> Missing Parts / Instructions, Shipping & Delivery -> Damaged, Shipping & Delivery -> Shipping Price Discrepancy, Others) |
| order.orderLines.orderLine.refund.refundCharges.refundCharge.charge | object | No | List of elements that make up a charge |
| order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.chargeType | string | No | The charge type for line items can be one of the following: PRODUCT or SHIPPING For details, refer to 'Charge Types' |
| order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.chargeName | string | No | If chargeType is PRODUCT, chargeName is Item Price. If chargeType is SHIPPING, chargeName is Shipping |
| order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.chargeAmount | object | No | The details for the amount of the tax charge |
| order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.chargeAmount.currency | string | No | The type of currency for the charge. Example: USD for US Dollars (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.chargeAmount.amount | number | No | The numerical amount for that charge. Example: 9.99 |
| order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.tax | object | No | Tax information for the charge, including taxName and taxAmount |
| order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.tax.taxName | string | No | The name associated with the tax. Example: 'Sales Tax' |
| order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.tax.taxAmount | object | No | The details for the amount of the tax charge |
| order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.tax.taxAmount.currency | string | No | The type of currency for the charge. Example: USD for US Dollars (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.tax.taxAmount.amount | number | No | The numerical amount for that charge. Example: 9.99 |
| order.orderLines.orderLine.originalCarrierMethod | string | No | Ship method stamped at order line level when order is placed |
| order.orderLines.orderLine.referenceLineId | string | No | Reference line Id |
| order.orderLines.orderLine.fulfillment | object | No | fulfillment information |
| order.orderLines.orderLine.fulfillment.fulfillmentOption | string | No | Example : S2H, S2S, etc. |
| order.orderLines.orderLine.fulfillment.shipMethod | string | No | Example : Value, Expedited, Standard, Rush, etc. |
| order.orderLines.orderLine.fulfillment.storeId | string | No | Store Id |
| order.orderLines.orderLine.fulfillment.pickUpDateTime | integer | No | Gives pick up datetime information |
| order.orderLines.orderLine.fulfillment.pickUpBy | string | No | Gives pick up by information |
| order.orderLines.orderLine.fulfillment.shippingProgramType | string | No | Gives shipping program information. Examples TWO_DAY, THREE_DAY |
| order.orderLines.orderLine.intentToCancel | string | No |  |
| order.orderLines.orderLine.configId | string | No | Sets ConfigID for Personalised orders |
| order.orderLines.orderLine.sellerOrderId | string | No | A unique ID associated with the sales order for specified Seller; gives Sellers the ability to print their own custom order ID on the return label; limit of 30 characters |
| order.paymentTypes | array<string> | No | Payment Types |
| order.orderSummary | object | No | Order Summary |
| order.orderSummary.totalAmount | object | No |  |
| order.orderSummary.totalAmount.currencyAmount | number | No |  |
| order.orderSummary.totalAmount.currencyUnit | string | No |  (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| order.orderSummary.orderSubTotals | array<object> | No |  |
| order.orderSummary.orderSubTotals.subTotalType | string | No |  |
| order.orderSummary.orderSubTotals.totalAmount | object | No |  |
| order.orderSummary.orderSubTotals.totalAmount.currencyAmount | number | No |  |
| order.orderSummary.orderSubTotals.totalAmount.currencyUnit | string | No |  (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| order.pickupPersons | array<object> | No | List of pickup persons |
| order.pickupPersons.name | object | No |  |
| order.pickupPersons.name.completeName | string | No |  |
| order.pickupPersons.name.firstName | string | No |  |
| order.pickupPersons.name.middleName | string | No |  |
| order.pickupPersons.name.lastName | string | No |  |
| order.pickupPersons.name.generalSuffix | string | No |  |
| order.pickupPersons.name.maturitySuffix | string | No |  |
| order.pickupPersons.name.titleOfRespect | string | No |  |
| order.pickupPersons.name.empty | boolean | No |  |
| order.pickupPersons.phone | object | No |  |
| order.pickupPersons.phone.id | uuid | No |  |
| order.pickupPersons.phone.areaCode | string | No |  |
| order.pickupPersons.phone.extension | string | No |  |
| order.pickupPersons.phone.completeNumber | string | No |  |
| order.pickupPersons.phone.type | string | No |  (MOBILE, HOME, WORK) |
| order.pickupPersons.phone.subscriberNumber | string | No |  |
| order.pickupPersons.phone.countryCode | string | No |  |
| order.shipNode | object | No | Specifies the type of shipNode |
| order.shipNode.type | string | No | Specifies the type of shipNode. Allowed values are SellerFulfilled, WFSFulfilled and 3PLFulfilled. |
| order.shipNode.name | string | No |  |
| order.shipNode.id | string | No |  |
