---
title: Get_Carrier_Rate_Quote
category: Fulfillment_Management
api_name: Get_Carrier_Rate_Quote
method: GET
path: /v3/fulfillment/carrier-rate-quotes
---

**Category:** Fulfillment_Management
**API:** Get_Carrier_Rate_Quote

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/fulfillment/carrier-rate-quotes

## API Description
Get Carrier Rate Quote

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| shipmentId (path) | string | Yes | Unique ID identifying each shipment. |
| mode (path) | string | Yes | Shipment type. |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| shipmentId | string | No |  |
| quoteId | string | No |  |
| estimatedDeliveryDateTime | date-time | No |  |
| quoteCreationDate | date-time | No |  |
| carrier | object | No |  |
| carrier.carrierId | string | No |  |
| carrier.carrierName | string | No |  |
| rateQuote | object | No |  |
| rateQuote.quoteId | string | No |  |
| rateQuote.estimatedDeliveryDateTime | date-time | No |  |
| rateQuote.carrier | object | No |  |
| rateQuote.carrier.carrierId | string | No |  |
| rateQuote.carrier.carrierName | string | No |  |
| rateQuote.currency | string | No |  |
| rateQuote.discountCharge | number | No |  |
| rateQuote.netCharge | number | No |  |
| rateQuote.surchargeType | string | No |  |
| rateQuote.surchargeValue | string | No |  |
| rateQuote.totalBillingWeight | number | No |  |
| rateQuote.status | string | No |  |
| rateQuote.transitDays | string | No |  |
| rateQuote.effectiveDate | date-time | No |  |
| rateQuote.expiryDate | date-time | No |  |
| rateQuote.mode | string | No |  |
| rateQuote.sellerFreightClassCode | string | No |  |
| rateQuote.freightCharge | number | No |  |
| rateQuote.fuelCharge | number | No |  |
| rateQuote.totalWeight | number | No |  |
| rateQuote.totalVolume | number | No |  |
| rateQuote.equipmentTypeCode | string | No |  |
| rateQuote.serviceCode | string | No |  |
| rateQuote.numberOfPallets | integer | No |  |
| rateQuote.nominalCharge | number | No |  |
| rateQuote.assessorialCharge | number | No |  |
| rateQuote.serviceCharge | number | No |  |
| rateQuote.minimumCharge | number | No |  |
| rateQuote.declaredValue | string | No |  |
| rateQuote.mixedSKUs | integer | No |  |
| rateQuote.singleSKUs | integer | No |  |
| rateQuote.freightReadyDate | date-time | No |  |
| shipmentPackages | array<object> | No |  |
| shipmentPackages.packageSequenceNumber | integer | No |  |
| shipmentPackages.weight | number | No |  |
| shipmentPackages.weightUOM | string | No |  |
| shipmentPackages.length | number | No |  |
| shipmentPackages.height | number | No |  |
| shipmentPackages.width | number | No |  |
| shipmentPackages.lengthUOM | string | No |  |
| shipmentPackages.labelInformation | object | No |  |
| shipmentPackages.labelInformation.labelData | string | No |  |
| shipmentPackages.labelInformation.labelFormat | string | No |  |
| shipmentPackages.labelInformation.trackingCode | string | No |  |
| shipmentPackages.labelInformation.referenceTrackingCode | string | No |  |
| shipmentPackages.labelInformation.epTrackerId | string | No |  |
| shipmentPackages.labelInformation.shipmentId | string | No |  |
| shipmentPackages.labelInformation.packageAsn | string | No |  |
| shipmentPackages.labelInformation.masterTrackingCode | string | No |  |
| shipmentPackages.labelInformation.master | boolean | No |  |
| shipmentPackages.billingWeight | number | No |  |
| shipmentPackages.netCharge | number | No |  |
| shipmentPackages.nominalCharge | number | No |  |
| shipmentPackages.assessorialCharge | number | No |  |
| shipmentPackages.serviceCharge | number | No |  |
| shipmentPackages.packageType | string | No |  |
| shipmentPackages.noOfPackages | integer | No |  |
| shipmentPackages.stackable | boolean | No |  |
| originLocation | object | No |  |
| originLocation.locationName | string | No |  |
| originLocation.address | object | No |  |
| originLocation.address.addressLine1 | string | No |  |
| originLocation.address.addressLine2 | string | No |  |
| originLocation.address.city | string | No |  |
| originLocation.address.stateCode | string | No |  |
| originLocation.address.countryCode | string | No |  |
| originLocation.address.postalCode | string | No |  |
| originLocation.address.phone | string | No |  |
| originLocation.locationId | string | No |  |
| destinationLocation | object | No |  |
| destinationLocation.locationName | string | No |  |
| destinationLocation.address | object | No |  |
| destinationLocation.address.addressLine1 | string | No |  |
| destinationLocation.address.addressLine2 | string | No |  |
| destinationLocation.address.city | string | No |  |
| destinationLocation.address.stateCode | string | No |  |
| destinationLocation.address.countryCode | string | No |  |
| destinationLocation.address.postalCode | string | No |  |
| destinationLocation.address.phone | string | No |  |
| destinationLocation.locationId | string | No |  |
| returnLocation | object | No |  |
| returnLocation.locationName | string | No |  |
| returnLocation.address | object | No |  |
| returnLocation.address.addressLine1 | string | No |  |
| returnLocation.address.addressLine2 | string | No |  |
| returnLocation.address.city | string | No |  |
| returnLocation.address.stateCode | string | No |  |
| returnLocation.address.countryCode | string | No |  |
| returnLocation.address.postalCode | string | No |  |
| returnLocation.address.phone | string | No |  |
