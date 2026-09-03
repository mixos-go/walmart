---
title: All_orders
category: Order_Management
api_name: All_orders
method: GET
path: /v3/orders
---

**Category:** Order_Management
**API:** All_orders

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/orders

## API Description
All orders

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| sku (query) | string | No | A seller-provided Product ID |
| customerOrderId (query) | string | No | The customer order ID |
| purchaseOrderId (query) | string | No | The purchase order ID. One customer may have multiple purchase orders. |
| status (query) | string | No | Status of purchase order line. Valid statuses are: Created, Acknowledged, Shipped, Delivered and Cancelled. |
| createdStartDate (query) | string | No | Fetches all purchase orders that were created after this date. Default is current date - 7 days. Use either UTC or ISO 8601 formats. Date example: '2020-03-16'(yyyy-MM-dd). Date with Timestamp example: '2020-03-16T10:30:15Z'(yyyy-MM-dd'T'HH:mm:ssZ). |
| createdEndDate (query) | string | No | Fetches all purchase orders that were created before this date. Default is current date. Use either UTC or ISO 8601 formats. Date example: '2020-03-16'(yyyy-MM-dd). Date with Timestamp example: '2020-03-16T10:30:15Z'(yyyy-MM-dd'T'HH:mm:ssZ). |
| fromExpectedShipDate (query) | string | No | Fetches all purchase orders that have order lines with an expected ship date after this date. Use either UTC or ISO 8601 formats. Date example: '2020-03-16'(yyyy-MM-dd). Date with Timestamp example: '2020-03-16T10:30:15Z'(yyyy-MM-dd'T'HH:mm:ssZ) |
| toExpectedShipDate (query) | string | No | Fetches all purchase orders that have order lines with an expected ship date before this date. Use either UTC or ISO 8601 formats. Date example: '2020-03-16'(yyyy-MM-dd). Date with Timestamp example: '2020-03-16T10:30:15Z'(yyyy-MM-dd'T'HH:mm:ssZ) |
| lastModifiedStartDate (query) | string | No | Fetches all purchase orders that were modified after this date. Use either UTC or ISO 8601 formats. Date example: '2020-03-16'(yyyy-MM-dd). Date with Timestamp example: '2020-03-16T10:30:15Z'(yyyy-MM-dd'T'HH:mm:ssZ). |
| lastModifiedEndDate (query) | string | No | Fetches all purchase orders that were modified before this date. Use either UTC or ISO 8601 formats. Date example: '2020-03-16'(yyyy-MM-dd). Date with Timestamp example: '2020-03-16T10:30:15Z'(yyyy-MM-dd'T'HH:mm:ssZ). |
| limit (query) | string | No | The number of orders to be returned. Cannot be larger than 200. |
| productInfo (query) | string | No | Provides the image URL and product weight in response, if available. Allowed values are true or false. |
| shipNodeType (query) | string | No | Specifies the type of shipNode. Allowed values are SellerFulfilled(Default), WFSFulfilled and 3PLFulfilled. |
| shippingProgramType (query) | string | No | Specifies the type of program. Allowed value is TWO_DAY. |
| replacementInfo (query) | string | No | Provides additional attributes - originalCustomerOrderID, orderType - related to Replacement order, in response, if available. Allowed values are true or false. |
| orderType (query) | string | No | Specifies if the order is a regular order or replacement order. Possible values are REGULAR or REPLACEMENT. Provided in response only if query parameter replacementInfo=true. |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| list | object | No | List of purchase orders in created state |
| list.errors | array<object> | No |  |
| list.errors.code | string | No |  |
| list.errors.field | string | No |  |
| list.errors.description | string | No |  |
| list.errors.info | string | No |  |
| list.errors.severity | string | No |  (INFO, WARN, ERROR) |
| list.errors.category | string | No |  (APPLICATION, SYSTEM, REQUEST, DATA) |
| list.errors.causes | array<object> | No |  |
| list.errors.causes.code | string | No |  |
| list.errors.causes.field | string | No |  |
| list.errors.causes.type | string | No |  |
| list.errors.causes.description | string | No |  |
| list.errors.errorIdentifiers | object | No |  |
| list.errors.component | string | No |  |
| list.errors.type | string | No |  |
| list.errors.serviceName | string | No |  |
| list.errors.gatewayErrorCategory | string | No |  (INTERNAL_DATA_ERROR, EXTERNAL_DATA_ERROR, SYSTEM_ERROR) |
| list.meta | object | No | Meta data about the list |
| list.meta.totalCount | integer | No | Total no of purchase orders. |
| list.meta.limit | integer | No | Number of purchase orders in the current page. |
| list.meta.nextCursor | string | No | String to be used as query parameter for getting next set of purchase orders, when more than 200 orders are retrieved. |
| list.elements | object | No | Information about the purchase order |
| list.elements.order | array<object> | No | Purchase Order List |
| list.elements.order.purchaseOrderId | string | No | A unique ID associated with the seller's purchase order |
| list.elements.order.customerOrderId | string | No | A unique ID associated with the sales order for specified customer |
| list.elements.order.customerEmailId | string | No | The email address of the customer for the sales order |
| list.elements.order.orderType | string | No | Specifies if the order is a regular order or replacement order. Possible values are REGULAR or REPLACEMENT. Provided in response only if query parameter replacementInfo=true. |
| list.elements.order.originalCustomerOrderID | string | No | customer order ID of the original customer order on which the replacement is created. |
| list.elements.order.orderDate | integer | No | The date the customer submitted the sales order |
| list.elements.order.buyerId | uuid | No | Unique ID associated with the specified buyer |
| list.elements.order.mart | string | No | Mart information |
| list.elements.order.isGuest | boolean | No | Indicates a guest customer |
| list.elements.order.shippingInfo | object | No | The shipping information provided by the customer to the seller |
| list.elements.order.shippingInfo.phone | string | No | The customer's phone number |
| list.elements.order.shippingInfo.estimatedDeliveryDate | integer | No | The estimated time and date for the delivery of the item. Format: yyyy-MM-ddThh:MM:ssZ Example: '2020-06-15T06:00:00Z' |
| list.elements.order.shippingInfo.estimatedShipDate | integer | No | The estimated time and date when the item will be shipped. Format: yyyy-MM-ddThh:MM:ssZ Example: '2020-06-15T06:00:00Z' |
| list.elements.order.shippingInfo.methodCode | string | No | The shipping method. Can be one of the following: Standard, Express, OneDay, WhiteGlove, Value or Freight (Standard, Express, OneDay, Freight, WhiteGlove, Value) |
| list.elements.order.shippingInfo.postalAddress | object | No | Elements of the customer's postal address |
| list.elements.order.shippingInfo.postalAddress.name | string | No | The name for the person/place of shipping address |
| list.elements.order.shippingInfo.postalAddress.address1 | string | No | The first line of the shipping address |
| list.elements.order.shippingInfo.postalAddress.address2 | string | No | The second line of the shipping address |
| list.elements.order.shippingInfo.postalAddress.city | string | No | The city of the shipping address |
| list.elements.order.shippingInfo.postalAddress.state | string | No | The state of the shipping address |
| list.elements.order.shippingInfo.postalAddress.postalCode | string | No | The zip code of the shipping address |
| list.elements.order.shippingInfo.postalAddress.country | string | No | The country of the shipping address |
| list.elements.order.shippingInfo.postalAddress.addressType | string | No | The address type, example: 'RESIDENTIAL' |
| list.elements.order.orderLines | object | No | A list of order lines in the order |
| list.elements.order.orderLines.orderLine | array<object> | No | A list of order lines in the order |
| list.elements.order.orderLines.orderLine.lineNumber | string | No | The line number associated with the details for each individual item in the purchase order |
| list.elements.order.orderLines.orderLine.item | object | No | The information for the item on the orderLine |
| list.elements.order.orderLines.orderLine.item.productName | string | No | The name of the product associated with the line item. Example: 'Kenmore CF1' or '2086883 Canister Secondary Filter Generic 2 Pack' |
| list.elements.order.orderLines.orderLine.item.sku | string | No | An arbitrary alphanumeric unique ID, assigned to each item in the item file |
| list.elements.order.orderLines.orderLine.item.imageUrl | string | No | Optional. Web URL for the image of the item. |
| list.elements.order.orderLines.orderLine.item.weight | object | No | Optional. Weight information for the item. |
| list.elements.order.orderLines.orderLine.item.weight.value | string | No | Numerical amount of weight parameter. |
| list.elements.order.orderLines.orderLine.item.weight.unit | string | No | Standard value of measurement of the item. Example: 'Pounds' |
| list.elements.order.orderLines.orderLine.charges | object | No | Information relating to the charge for the orderLine |
| list.elements.order.orderLines.orderLine.charges.charge | array<object> | No | Information relating to the charge for the orderLine |
| list.elements.order.orderLines.orderLine.charges.charge.chargeType | string | No | The charge type for line items can be one of the following: PRODUCT or SHIPPING For details, refer to 'Charge Types' |
| list.elements.order.orderLines.orderLine.charges.charge.chargeName | string | No | If chargeType is PRODUCT, chargeName is Item Price. If chargeType is SHIPPING, chargeName is Shipping |
| list.elements.order.orderLines.orderLine.charges.charge.chargeAmount | object | No | The details for the amount of the tax charge |
| list.elements.order.orderLines.orderLine.charges.charge.chargeAmount.currency | string | No | The type of currency for the charge. Example: USD for US Dollars (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| list.elements.order.orderLines.orderLine.charges.charge.chargeAmount.amount | number | No | The numerical amount for that charge. Example: 9.99 |
| list.elements.order.orderLines.orderLine.charges.charge.tax | object | No | Tax information for the charge, including taxName and taxAmount |
| list.elements.order.orderLines.orderLine.charges.charge.tax.taxName | string | No | The name associated with the tax. Example: 'Sales Tax' |
| list.elements.order.orderLines.orderLine.charges.charge.tax.taxAmount | object | No | The details for the amount of the tax charge |
| list.elements.order.orderLines.orderLine.charges.charge.tax.taxAmount.currency | string | No | The type of currency for the charge. Example: USD for US Dollars (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| list.elements.order.orderLines.orderLine.charges.charge.tax.taxAmount.amount | number | No | The numerical amount for that charge. Example: 9.99 |
| list.elements.order.orderLines.orderLine.orderLineQuantity | object | No | Details about the status update |
| list.elements.order.orderLines.orderLine.orderLineQuantity.unitOfMeasurement | string | No | Unit of quantity (EACH, EA) |
| list.elements.order.orderLines.orderLine.orderLineQuantity.amount | string | No | Always use '1' |
| list.elements.order.orderLines.orderLine.statusDate | integer | No | The date shown on the recent order status |
| list.elements.order.orderLines.orderLine.orderLineStatuses | object | No | A list of statuses for the Order Line |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus | array<object> | No | Detail List of Order Line status |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.status | string | No | Should be 'Created' (Created, Acknowledged, Shipped, Delivered, Cancelled, Refund) |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.statusQuantity | object | No | Details about the status update |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.statusQuantity.unitOfMeasurement | string | No | Unit of quantity (EACH, EA) |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.statusQuantity.amount | string | No | Always use '1' |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.cancellationReason | string | No | If order is cancelled, cancellationReason will explain the reason |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo | object | No | List of information about the package shipment and tracking updates |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.shipDateTime | integer | No | The date the package was shipped |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.carrierName | object | No | Information about the package carrier(s) |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.carrierName.otherCarrier | string | No | Other carrier name, When otherCarrier is used, trackingUrl must also be provided |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.carrierName.carrier | string | No | The package shipment carrier. Valid entries are: UPS, USPS, FedEx, Airborne, OnTrac, DHL Ecommerce - US, LS (LaserShip), UDS (United Delivery Service), UPSMI (UPS Mail Innovations), FDX, PILOT, ESTES, SAIA, FDS Express, Seko Worldwide, HIT Delivery, FEDEXSP (FedEx SmartPost), RL Carriers, Metropolit (UPS, USPS, FedEx, Airborne, OnTrac, DHL Ecommerce - US, LS, UDS, UPSMI, FDX, PILOT, ESTES, SAIA, FDS Express, Seko Worldwide, HIT Delivery, FEDEXSP, RL Carriers, Metropolitan Warehouse & Delivery, China Post, YunExpress, Yellow Freight Sys, AIT Worldwide Logistics, Chukou1, Sendle, Landmark Global, Sunyou, Yanwen, 4PX, GLS, OSM Worldwide, FIRST MILE, AM Trucking, CEVA, India Post, SF Express, CNE, TForce Freight, AxleHire, LSO) |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.methodCode | string | No | The shipping method. Can be one of the following: Standard, Express, OneDay, WhiteGlove, Value or Freight (Standard, Express, OneDay, Freight, WhiteGlove, Value) |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.trackingNumber | string | No | The shipment tracking number |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.trackingURL | string | No | The URL for tracking the shipment. This parameter is mandatory if the otherCarrier parameter is used |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress | object | No | Gives Sellers the ability to specify the RC center address during fulfillment; any returns created for the PO will always be returned to the RC address specified |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.name | string | No | The name for the person/place of return address |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.address1 | string | No | The first line of the return address |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.address2 | string | No | The second line of the return address |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.city | string | No | The city of the return address |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.state | string | No | The state of the return address |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.postalCode | string | No | The zip code of the return address |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.country | string | No | The country of the return address |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.dayPhone | string | No | Phone of the center where the package shipment is returned |
| list.elements.order.orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.emailId | string | No | Email of the center where the package shipment is returned |
| list.elements.order.orderLines.orderLine.returnOrderId | string | No | Id of the return order created in case of a full refund |
| list.elements.order.orderLines.orderLine.refund | object | No | Details about any partial refund on the order |
| list.elements.order.orderLines.orderLine.refund.refundId | string | No |  |
| list.elements.order.orderLines.orderLine.refund.refundComments | string | No |  |
| list.elements.order.orderLines.orderLine.refund.refundCharges | object | No |  |
| list.elements.order.orderLines.orderLine.refund.refundCharges.refundCharge | array<object> | No |  |
| list.elements.order.orderLines.orderLine.refund.refundCharges.refundCharge.refundReason | string | No |  (BillingError, TaxExemptCustomer, ItemNotAsAdvertised, IncorrectItemReceived, CancelledYetShipped, ItemNotReceivedByCustomer, IncorrectShippingPrice, DamagedItem, DefectiveItem, CustomerChangedMind, CustomerReceivedItemLate, Missing Parts / Instructions, Finance -> Goodwill, Finance -> Rollback, Buyer canceled, Customer returned item, General adjustment, Merchandise not received, Quality -> Missing Parts / Instructions, Shipping & Delivery -> Damaged, Shipping & Delivery -> Shipping Price Discrepancy, Others) |
| list.elements.order.orderLines.orderLine.refund.refundCharges.refundCharge.charge | object | No | List of elements that make up a charge |
| list.elements.order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.chargeType | string | No | The charge type for line items can be one of the following: PRODUCT or SHIPPING For details, refer to 'Charge Types' |
| list.elements.order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.chargeName | string | No | If chargeType is PRODUCT, chargeName is Item Price. If chargeType is SHIPPING, chargeName is Shipping |
| list.elements.order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.chargeAmount | object | No | The details for the amount of the tax charge |
| list.elements.order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.chargeAmount.currency | string | No | The type of currency for the charge. Example: USD for US Dollars (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| list.elements.order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.chargeAmount.amount | number | No | The numerical amount for that charge. Example: 9.99 |
| list.elements.order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.tax | object | No | Tax information for the charge, including taxName and taxAmount |
| list.elements.order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.tax.taxName | string | No | The name associated with the tax. Example: 'Sales Tax' |
| list.elements.order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.tax.taxAmount | object | No | The details for the amount of the tax charge |
| list.elements.order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.tax.taxAmount.currency | string | No | The type of currency for the charge. Example: USD for US Dollars (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| list.elements.order.orderLines.orderLine.refund.refundCharges.refundCharge.charge.tax.taxAmount.amount | number | No | The numerical amount for that charge. Example: 9.99 |
| list.elements.order.orderLines.orderLine.originalCarrierMethod | string | No | Ship method stamped at order line level when order is placed |
| list.elements.order.orderLines.orderLine.referenceLineId | string | No | Reference line Id |
| list.elements.order.orderLines.orderLine.fulfillment | object | No | fulfillment information |
| list.elements.order.orderLines.orderLine.fulfillment.fulfillmentOption | string | No | Example : S2H, S2S, etc. |
| list.elements.order.orderLines.orderLine.fulfillment.shipMethod | string | No | Example : Value, Expedited, Standard, Rush, etc. |
| list.elements.order.orderLines.orderLine.fulfillment.storeId | string | No | Store Id |
| list.elements.order.orderLines.orderLine.fulfillment.pickUpDateTime | integer | No | Gives pick up datetime information |
| list.elements.order.orderLines.orderLine.fulfillment.pickUpBy | string | No | Gives pick up by information |
| list.elements.order.orderLines.orderLine.fulfillment.shippingProgramType | string | No | Gives shipping program information. Examples TWO_DAY, THREE_DAY |
| list.elements.order.orderLines.orderLine.intentToCancel | string | No |  |
| list.elements.order.orderLines.orderLine.configId | string | No | Sets ConfigID for Personalised orders |
| list.elements.order.orderLines.orderLine.sellerOrderId | string | No | A unique ID associated with the sales order for specified Seller; gives Sellers the ability to print their own custom order ID on the return label; limit of 30 characters |
| list.elements.order.paymentTypes | array<string> | No | Payment Types |
| list.elements.order.orderSummary | object | No | Order Summary |
| list.elements.order.orderSummary.totalAmount | object | No |  |
| list.elements.order.orderSummary.totalAmount.currencyAmount | number | No |  |
| list.elements.order.orderSummary.totalAmount.currencyUnit | string | No |  (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| list.elements.order.orderSummary.orderSubTotals | array<object> | No |  |
| list.elements.order.orderSummary.orderSubTotals.subTotalType | string | No |  |
| list.elements.order.orderSummary.orderSubTotals.totalAmount | object | No |  |
| list.elements.order.orderSummary.orderSubTotals.totalAmount.currencyAmount | number | No |  |
| list.elements.order.orderSummary.orderSubTotals.totalAmount.currencyUnit | string | No |  (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| list.elements.order.pickupPersons | array<object> | No | List of pickup persons |
| list.elements.order.pickupPersons.name | object | No |  |
| list.elements.order.pickupPersons.name.completeName | string | No |  |
| list.elements.order.pickupPersons.name.firstName | string | No |  |
| list.elements.order.pickupPersons.name.middleName | string | No |  |
| list.elements.order.pickupPersons.name.lastName | string | No |  |
| list.elements.order.pickupPersons.name.generalSuffix | string | No |  |
| list.elements.order.pickupPersons.name.maturitySuffix | string | No |  |
| list.elements.order.pickupPersons.name.titleOfRespect | string | No |  |
| list.elements.order.pickupPersons.name.empty | boolean | No |  |
| list.elements.order.pickupPersons.phone | object | No |  |
| list.elements.order.pickupPersons.phone.id | uuid | No |  |
| list.elements.order.pickupPersons.phone.areaCode | string | No |  |
| list.elements.order.pickupPersons.phone.extension | string | No |  |
| list.elements.order.pickupPersons.phone.completeNumber | string | No |  |
| list.elements.order.pickupPersons.phone.type | string | No |  (MOBILE, HOME, WORK) |
| list.elements.order.pickupPersons.phone.subscriberNumber | string | No |  |
| list.elements.order.pickupPersons.phone.countryCode | string | No |  |
| list.elements.order.shipNode | object | No | Specifies the type of shipNode |
| list.elements.order.shipNode.type | string | No | Specifies the type of shipNode. Allowed values are SellerFulfilled, WFSFulfilled and 3PLFulfilled. |
| list.elements.order.shipNode.name | string | No |  |
| list.elements.order.shipNode.id | string | No |  |
