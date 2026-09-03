---
title: An_order
category: Order_Management
api_name: An_order
method: GET
path: /v3/orders/{purchaseOrderId}
---

**Category:** Order_Management
**API:** An_order

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/orders/{purchaseOrderId}

## API Description
An order

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| purchaseOrderId (path) | string | Yes | purchaseOrderId |
| productInfo (query) | string | No | Provides the image URL and product weight in response, if available. Allowed values are true or false. |
| replacementInfo (query) | string | No | Provides additional attributes - originalCustomerOrderID, orderType - related to Replacement order, in response, if available. Allowed values are true or false. |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| purchaseOrderId | string | Yes | A unique ID associated with the seller's purchase order |
| customerOrderId | string | Yes | A unique ID associated with the sales order for specified customer |
| customerEmailId | string | Yes | The email address of the customer for the sales order |
| orderDate | date-time | Yes | The date the customer submitted the sales order |
| buyerId | uuid | No | Unique ID associated with the specified buyer |
| mart | string | No | Mart information |
| isGuest | boolean | No | Indicates a guest customer |
| shippingInfo | object | Yes | The shipping information provided by the customer to the seller |
| shippingInfo.phone | string | No | The customer's phone number |
| shippingInfo.estimatedDeliveryDate | integer | No | The estimated time and date for the delivery of the item. Format: yyyy-MM-ddThh:MM:ssZ Example: '2020-06-15T06:00:00Z' |
| shippingInfo.estimatedShipDate | integer | No | The estimated time and date when the item will be shipped. Format: yyyy-MM-ddThh:MM:ssZ Example: '2020-06-15T06:00:00Z' |
| shippingInfo.methodCode | string | No | The shipping method. Can be one of the following: Standard, Express, OneDay, WhiteGlove, Value or Freight (Standard, Express, OneDay, Freight, WhiteGlove, Value) |
| shippingInfo.postalAddress | object | No | Elements of the customer's postal address |
| shippingInfo.postalAddress.name | string | No | The name for the person/place of shipping address |
| shippingInfo.postalAddress.address1 | string | No | The first line of the shipping address |
| shippingInfo.postalAddress.address2 | string | No | The second line of the shipping address |
| shippingInfo.postalAddress.city | string | No | The city of the shipping address |
| shippingInfo.postalAddress.state | string | No | The state of the shipping address |
| shippingInfo.postalAddress.postalCode | string | No | The zip code of the shipping address |
| shippingInfo.postalAddress.country | string | No | The country of the shipping address |
| shippingInfo.postalAddress.addressType | string | No | The address type, example: 'RESIDENTIAL' |
| orderLines | object | Yes | A list of order lines in the order |
| orderLines.orderLine | array<object> | No | A list of order lines in the order |
| orderLines.orderLine.lineNumber | string | No | The line number associated with the details for each individual item in the purchase order |
| orderLines.orderLine.item | object | No | The information for the item on the orderLine |
| orderLines.orderLine.item.productName | string | No | The name of the product associated with the line item. Example: 'Kenmore CF1' or '2086883 Canister Secondary Filter Generic 2 Pack' |
| orderLines.orderLine.item.sku | string | No | An arbitrary alphanumeric unique ID, assigned to each item in the item file |
| orderLines.orderLine.item.imageUrl | string | No | Optional. Web URL for the image of the item. |
| orderLines.orderLine.item.weight | object | No | Optional. Weight information for the item. |
| orderLines.orderLine.item.weight.value | string | No | Numerical amount of weight parameter. |
| orderLines.orderLine.item.weight.unit | string | No | Standard value of measurement of the item. Example: 'Pounds' |
| orderLines.orderLine.charges | object | No | Information relating to the charge for the orderLine |
| orderLines.orderLine.charges.charge | array<object> | No | Information relating to the charge for the orderLine |
| orderLines.orderLine.charges.charge.chargeType | string | No | The charge type for line items can be one of the following: PRODUCT or SHIPPING For details, refer to 'Charge Types' |
| orderLines.orderLine.charges.charge.chargeName | string | No | If chargeType is PRODUCT, chargeName is Item Price. If chargeType is SHIPPING, chargeName is Shipping |
| orderLines.orderLine.charges.charge.chargeAmount | object | No | The details for the amount of the tax charge |
| orderLines.orderLine.charges.charge.chargeAmount.currency | string | No | The type of currency for the charge. Example: USD for US Dollars (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| orderLines.orderLine.charges.charge.chargeAmount.amount | number | No | The numerical amount for that charge. Example: 9.99 |
| orderLines.orderLine.charges.charge.tax | object | No | Tax information for the charge, including taxName and taxAmount |
| orderLines.orderLine.charges.charge.tax.taxName | string | No | The name associated with the tax. Example: 'Sales Tax' |
| orderLines.orderLine.charges.charge.tax.taxAmount | object | No | The details for the amount of the tax charge |
| orderLines.orderLine.charges.charge.tax.taxAmount.currency | string | No | The type of currency for the charge. Example: USD for US Dollars (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| orderLines.orderLine.charges.charge.tax.taxAmount.amount | number | No | The numerical amount for that charge. Example: 9.99 |
| orderLines.orderLine.orderLineQuantity | object | No | Details about the status update |
| orderLines.orderLine.orderLineQuantity.unitOfMeasurement | string | No | Unit of quantity (EACH, EA) |
| orderLines.orderLine.orderLineQuantity.amount | string | No | Always use '1' |
| orderLines.orderLine.statusDate | integer | No | The date shown on the recent order status |
| orderLines.orderLine.orderLineStatuses | object | No | A list of statuses for the Order Line |
| orderLines.orderLine.orderLineStatuses.orderLineStatus | array<object> | No | Detail List of Order Line status |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.status | string | No | Should be 'Created' (Created, Acknowledged, Shipped, Delivered, Cancelled, Refund) |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.statusQuantity | object | No | Details about the status update |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.statusQuantity.unitOfMeasurement | string | No | Unit of quantity (EACH, EA) |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.statusQuantity.amount | string | No | Always use '1' |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.cancellationReason | string | No | If order is cancelled, cancellationReason will explain the reason |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo | object | No | List of information about the package shipment and tracking updates |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.shipDateTime | integer | No | The date the package was shipped |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.carrierName | object | No | Information about the package carrier(s) |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.carrierName.otherCarrier | string | No | Other carrier name, When otherCarrier is used, trackingUrl must also be provided |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.carrierName.carrier | string | No | The package shipment carrier. Valid entries are: UPS, USPS, FedEx, Airborne, OnTrac, DHL Ecommerce - US, LS (LaserShip), UDS (United Delivery Service), UPSMI (UPS Mail Innovations), FDX, PILOT, ESTES, SAIA, FDS Express, Seko Worldwide, HIT Delivery, FEDEXSP (FedEx SmartPost), RL Carriers, Metropolit (UPS, USPS, FedEx, Airborne, OnTrac, DHL Ecommerce - US, LS, UDS, UPSMI, FDX, PILOT, ESTES, SAIA, FDS Express, Seko Worldwide, HIT Delivery, FEDEXSP, RL Carriers, Metropolitan Warehouse & Delivery, China Post, YunExpress, Yellow Freight Sys, AIT Worldwide Logistics, Chukou1, Sendle, Landmark Global, Sunyou, Yanwen, 4PX, GLS, OSM Worldwide, FIRST MILE, AM Trucking, CEVA, India Post, SF Express, CNE, TForce Freight, AxleHire, LSO) |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.methodCode | string | No | The shipping method. Can be one of the following: Standard, Express, OneDay, WhiteGlove, Value or Freight (Standard, Express, OneDay, Freight, WhiteGlove, Value) |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.trackingNumber | string | No | The shipment tracking number |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.trackingInfo.trackingURL | string | No | The URL for tracking the shipment. This parameter is mandatory if the otherCarrier parameter is used |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress | object | No | Gives Sellers the ability to specify the RC center address during fulfillment; any returns created for the PO will always be returned to the RC address specified |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.name | string | No | The name for the person/place of return address |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.address1 | string | No | The first line of the return address |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.address2 | string | No | The second line of the return address |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.city | string | No | The city of the return address |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.state | string | No | The state of the return address |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.postalCode | string | No | The zip code of the return address |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.country | string | No | The country of the return address |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.dayPhone | string | No | Phone of the center where the package shipment is returned |
| orderLines.orderLine.orderLineStatuses.orderLineStatus.returnCenterAddress.emailId | string | No | Email of the center where the package shipment is returned |
| orderLines.orderLine.returnOrderId | string | No | Id of the return order created in case of a full refund |
| orderLines.orderLine.refund | object | No | Details about any partial refund on the order |
| orderLines.orderLine.refund.refundId | string | No |  |
| orderLines.orderLine.refund.refundComments | string | No |  |
| orderLines.orderLine.refund.refundCharges | object | No |  |
| orderLines.orderLine.refund.refundCharges.refundCharge | array<object> | No |  |
| orderLines.orderLine.refund.refundCharges.refundCharge.refundReason | string | No |  (BillingError, TaxExemptCustomer, ItemNotAsAdvertised, IncorrectItemReceived, CancelledYetShipped, ItemNotReceivedByCustomer, IncorrectShippingPrice, DamagedItem, DefectiveItem, CustomerChangedMind, CustomerReceivedItemLate, Missing Parts / Instructions, Finance -> Goodwill, Finance -> Rollback, Buyer canceled, Customer returned item, General adjustment, Merchandise not received, Quality -> Missing Parts / Instructions, Shipping & Delivery -> Damaged, Shipping & Delivery -> Shipping Price Discrepancy, Others) |
| orderLines.orderLine.refund.refundCharges.refundCharge.charge | object | No | List of elements that make up a charge |
| orderLines.orderLine.refund.refundCharges.refundCharge.charge.chargeType | string | No | The charge type for line items can be one of the following: PRODUCT or SHIPPING For details, refer to 'Charge Types' |
| orderLines.orderLine.refund.refundCharges.refundCharge.charge.chargeName | string | No | If chargeType is PRODUCT, chargeName is Item Price. If chargeType is SHIPPING, chargeName is Shipping |
| orderLines.orderLine.refund.refundCharges.refundCharge.charge.chargeAmount | object | No | The details for the amount of the tax charge |
| orderLines.orderLine.refund.refundCharges.refundCharge.charge.chargeAmount.currency | string | No | The type of currency for the charge. Example: USD for US Dollars (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| orderLines.orderLine.refund.refundCharges.refundCharge.charge.chargeAmount.amount | number | No | The numerical amount for that charge. Example: 9.99 |
| orderLines.orderLine.refund.refundCharges.refundCharge.charge.tax | object | No | Tax information for the charge, including taxName and taxAmount |
| orderLines.orderLine.refund.refundCharges.refundCharge.charge.tax.taxName | string | No | The name associated with the tax. Example: 'Sales Tax' |
| orderLines.orderLine.refund.refundCharges.refundCharge.charge.tax.taxAmount | object | No | The details for the amount of the tax charge |
| orderLines.orderLine.refund.refundCharges.refundCharge.charge.tax.taxAmount.currency | string | No | The type of currency for the charge. Example: USD for US Dollars (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| orderLines.orderLine.refund.refundCharges.refundCharge.charge.tax.taxAmount.amount | number | No | The numerical amount for that charge. Example: 9.99 |
| orderLines.orderLine.originalCarrierMethod | string | No | Ship method stamped at order line level when order is placed |
| orderLines.orderLine.referenceLineId | string | No | Reference line Id |
| orderLines.orderLine.fulfillment | object | No | fulfillment information |
| orderLines.orderLine.fulfillment.fulfillmentOption | string | No | Example : S2H, S2S, etc. |
| orderLines.orderLine.fulfillment.shipMethod | string | No | Example : Value, Expedited, Standard, Rush, etc. |
| orderLines.orderLine.fulfillment.storeId | string | No | Store Id |
| orderLines.orderLine.fulfillment.pickUpDateTime | integer | No | Gives pick up datetime information |
| orderLines.orderLine.fulfillment.pickUpBy | string | No | Gives pick up by information |
| orderLines.orderLine.fulfillment.shippingProgramType | string | No | Gives shipping program information. Examples TWO_DAY, THREE_DAY |
| orderLines.orderLine.intentToCancel | string | No |  |
| orderLines.orderLine.configId | string | No | Sets ConfigID for Personalised orders |
| orderLines.orderLine.sellerOrderId | string | No | A unique ID associated with the sales order for specified Seller; gives Sellers the ability to print their own custom order ID on the return label; limit of 30 characters |
| paymentTypes | array<string> | No | Payment Types |
| orderSummary | object | No | Order Summary |
| orderSummary.totalAmount | object | No |  |
| orderSummary.totalAmount.currencyAmount | number | No |  |
| orderSummary.totalAmount.currencyUnit | string | No |  (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| orderSummary.orderSubTotals | array<object> | No |  |
| orderSummary.orderSubTotals.subTotalType | string | No |  |
| orderSummary.orderSubTotals.totalAmount | object | No |  |
| orderSummary.orderSubTotals.totalAmount.currencyAmount | number | No |  |
| orderSummary.orderSubTotals.totalAmount.currencyUnit | string | No |  (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| pickupPersons | array<object> | No | List of pickup persons |
| pickupPersons.name | object | No |  |
| pickupPersons.name.completeName | string | No |  |
| pickupPersons.name.firstName | string | No |  |
| pickupPersons.name.middleName | string | No |  |
| pickupPersons.name.lastName | string | No |  |
| pickupPersons.name.generalSuffix | string | No |  |
| pickupPersons.name.maturitySuffix | string | No |  |
| pickupPersons.name.titleOfRespect | string | No |  |
| pickupPersons.name.empty | boolean | No |  |
| pickupPersons.phone | object | No |  |
| pickupPersons.phone.id | uuid | No |  |
| pickupPersons.phone.areaCode | string | No |  |
| pickupPersons.phone.extension | string | No |  |
| pickupPersons.phone.completeNumber | string | No |  |
| pickupPersons.phone.type | string | No |  (MOBILE, HOME, WORK) |
| pickupPersons.phone.subscriberNumber | string | No |  |
| pickupPersons.phone.countryCode | string | No |  |
| shipNode | object | No | Specifies the type of shipNode |
| shipNode.type | string | No | Specifies the type of shipNode. Allowed values are SellerFulfilled, WFSFulfilled and 3PLFulfilled. |
| shipNode.name | string | No |  |
| shipNode.id | string | No |  |
