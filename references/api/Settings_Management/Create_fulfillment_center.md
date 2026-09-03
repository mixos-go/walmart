---
title: Create_fulfillment_center
category: Settings_Management
api_name: Create_fulfillment_center
method: POST
path: /v3/settings/shipping/shipnodes
---

**Category:** Settings_Management
**API:** Create_fulfillment_center

**Method:** POST
**HTTP Path:** https://marketplace.walmartapis.com/v3/settings/shipping/shipnodes

## API Description
Create fulfillment center

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| shipNodeHeader | object | No |  |
| shipNodeHeader.version | string | No |  |
| shipNode | array<object> | No |  |
| shipNode.shipNodeName | string | No | Name of the fulfillment center. |
| shipNode.status | string | No | Status of fulfillment center. Allowed values: ACTIVE, INACTIVE.. |
| shipNode.timeZone | string | No | Time zone that the seller ships from.Allowed timezones are PST, EST, CST, MST. |
| shipNode.distributorSupportedServices | array<string> | No | The services supported by the defined physical ship node . The allowed values: TWO_DAY_DELIVERY. |
| shipNode.customNodeId | string | No | Custom node identifier provided by seller. Allowed values are alphanumeric \| String |
| shipNode.postalAddress | object | No | Postal code of the fulfillment center. |
| shipNode.postalAddress.addressLine1 | string | No | Street address of the fulfillment center. |
| shipNode.postalAddress.city | string | No | City of the fulfillment center. |
| shipNode.postalAddress.state | string | No | State of the fulfillment center. |
| shipNode.postalAddress.country | string | No | Country of the fulfillment center. |
| shipNode.postalAddress.postalCode | string | No | Postal code of the fulfillment center. |
| shipNode.shippingDetails | array<object> | No | Shipping Details. |
| shipNode.shippingDetails.twoDayShipping | array<object> | No | Shipping type provided. |
| shipNode.shippingDetails.twoDayShipping.carrierMethodName | string | No | Name of the shipping carrier. Carrier names can be retrieved from the Get carrier methods API. |
| shipNode.shippingDetails.twoDayShipping.carrierMethodType | string | No | Shipping method. |
| shipNode.calendarDayConfiguration | object | No | Calendar day promise details. For examples, please refer to 'Sample 2 - Calendar Day Configurations' in request & response samples. |
| shipNode.calendarDayConfiguration.standardProcessingSchedule | object | No | Operating Schedule for the fulfillment center |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.sunday | object | No |  |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.sunday.isWorkingDay | boolean | No | Flag to specify if shipNode is operational on the specified day of each week. Allowed values are true or false. |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.sunday.cutOffTime | HH:mm | No | Order processing cutoff time. Please note that cutoff time is respective of the seller’s time zone. If not provided in the request body, then by default it will be set to '14:00'. Example: '09:30'(HH:mm) |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.monday | object | No |  |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.monday.isWorkingDay | boolean | No | Flag to specify if shipNode is operational on the specified day of each week. Allowed values are true or false. |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.monday.cutOffTime | HH:mm | No | Order processing cutoff time. Please note that cutoff time is respective of the seller’s time zone. If not provided in the request body, then by default it will be set to '14:00'. Example: '09:30'(HH:mm) |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.tuesday | object | No |  |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.tuesday.isWorkingDay | boolean | No | Flag to specify if shipNode is operational on the specified day of each week. Allowed values are true or false. |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.tuesday.cutOffTime | HH:mm | No | Order processing cutoff time. Please note that cutoff time is respective of the seller’s time zone. If not provided in the request body, then by default it will be set to '14:00'. Example: '09:30'(HH:mm) |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.wednesday | object | No |  |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.wednesday.isWorkingDay | boolean | No | Flag to specify if shipNode is operational on the specified day of each week. Allowed values are true or false. |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.wednesday.cutOffTime | HH:mm | No | Order processing cutoff time. Please note that cutoff time is respective of the seller’s time zone. If not provided in the request body, then by default it will be set to '14:00'. Example: '09:30'(HH:mm) |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.thursday | object | No |  |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.thursday.isWorkingDay | boolean | No | Flag to specify if shipNode is operational on the specified day of each week. Allowed values are true or false. |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.thursday.cutOffTime | HH:mm | No | Order processing cutoff time. Please note that cutoff time is respective of the seller’s time zone. If not provided in the request body, then by default it will be set to '14:00'. Example: '09:30'(HH:mm) |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.friday | object | No |  |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.friday.isWorkingDay | boolean | No | Flag to specify if shipNode is operational on the specified day of each week. Allowed values are true or false. |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.friday.cutOffTime | HH:mm | No | Order processing cutoff time. Please note that cutoff time is respective of the seller’s time zone. If not provided in the request body, then by default it will be set to '14:00'. Example: '09:30'(HH:mm) |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.saturday | object | No |  |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.saturday.isWorkingDay | boolean | No | Flag to specify if shipNode is operational on the specified day of each week. Allowed values are true or false. |
| shipNode.calendarDayConfiguration.standardProcessingSchedule.saturday.cutOffTime | HH:mm | No | Order processing cutoff time. Please note that cutoff time is respective of the seller’s time zone. If not provided in the request body, then by default it will be set to '14:00'. Example: '09:30'(HH:mm) |
| shipNode.calendarDayConfiguration.additionalDaysOff | array<string> | No | List of additional days on which the fulfillment center is closed. For example, if the fulfillment center is closed on New Year’s Day, then add the date in the list. If there are no additional off days, then this list will be empty. Use ISO 8601 format for date. For example: '2021-07-16'(yyyy-MM-dd) |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| shipNode | string | No | The fulfillment center or ship node Id which uniquely identifies each facility and is autogenerated during the creation of fulfillment center. Every time a facility is added, a new ship node id is generated. |
| nodeType | string | No | Defines if the fulfillment center is virtual, seller owned or third party owned. Allowed values: PHYSICAL, VIRTUAL, 3PL. |
| shipNodeName | string | No | Name of the fulfillment center. |
| status | string | No | Status of fulfillment center. Allowed values: ACTIVE, INACTIVE.. |
| timeZone | string | No | Time zone that the seller ships from.Allowed timezones are PST, EST, CST, MST. |
| distributorSupportedServices | array<string> | No | The services supported by the defined physical ship node . The allowed values: TWO_DAY_DELIVERY. |
| customNodeId | string | No | Custom node identifier provided by seller. Allowed values are alphanumeric \| String |
| postalAddress | object | No | Postal code of the fulfillment center. |
| postalAddress.addressLine1 | string | No | Street address of the fulfillment center. |
| postalAddress.city | string | No | City of the fulfillment center. |
| postalAddress.state | string | No | State of the fulfillment center. |
| postalAddress.country | string | No | Country of the fulfillment center. |
| postalAddress.postalCode | string | No | Postal code of the fulfillment center. |
| shippingDetails | array<object> | No | Shipping Details. |
| shippingDetails.twoDayShipping | array<object> | No | Shipping type provided. |
| shippingDetails.twoDayShipping.carrierMethodName | string | No | Name of the shipping carrier. Carrier names can be retrieved from the Get carrier methods API. |
| shippingDetails.twoDayShipping.carrierMethodType | string | No | Shipping method. |
| calendarDayConfiguration | object | No | Calendar day promise details. For examples, please refer to 'Sample 2 - Calendar Day Configurations' in request & response samples. |
| calendarDayConfiguration.standardProcessingSchedule | object | No | Operating Schedule for the fulfillment center |
| calendarDayConfiguration.standardProcessingSchedule.sunday | object | No |  |
| calendarDayConfiguration.standardProcessingSchedule.sunday.isWorkingDay | boolean | No | Flag to specify if shipNode is operational on the specified day of each week. Allowed values are true or false. |
| calendarDayConfiguration.standardProcessingSchedule.sunday.cutOffTime | HH:mm | No | Order processing cutoff time. Please note that cutoff time is respective of the seller’s time zone. Example: '09:30'(HH:mm) |
| calendarDayConfiguration.standardProcessingSchedule.monday | object | No |  |
| calendarDayConfiguration.standardProcessingSchedule.monday.isWorkingDay | boolean | No | Flag to specify if shipNode is operational on the specified day of each week. Allowed values are true or false. |
| calendarDayConfiguration.standardProcessingSchedule.monday.cutOffTime | HH:mm | No | Order processing cutoff time. Please note that cutoff time is respective of the seller’s time zone. Example: '09:30'(HH:mm) |
| calendarDayConfiguration.standardProcessingSchedule.tuesday | object | No |  |
| calendarDayConfiguration.standardProcessingSchedule.tuesday.isWorkingDay | boolean | No | Flag to specify if shipNode is operational on the specified day of each week. Allowed values are true or false. |
| calendarDayConfiguration.standardProcessingSchedule.tuesday.cutOffTime | HH:mm | No | Order processing cutoff time. Please note that cutoff time is respective of the seller’s time zone. Example: '09:30'(HH:mm) |
| calendarDayConfiguration.standardProcessingSchedule.wednesday | object | No |  |
| calendarDayConfiguration.standardProcessingSchedule.wednesday.isWorkingDay | boolean | No | Flag to specify if shipNode is operational on the specified day of each week. Allowed values are true or false. |
| calendarDayConfiguration.standardProcessingSchedule.wednesday.cutOffTime | HH:mm | No | Order processing cutoff time. Please note that cutoff time is respective of the seller’s time zone. Example: '09:30'(HH:mm) |
| calendarDayConfiguration.standardProcessingSchedule.thursday | object | No |  |
| calendarDayConfiguration.standardProcessingSchedule.thursday.isWorkingDay | boolean | No | Flag to specify if shipNode is operational on the specified day of each week. Allowed values are true or false. |
| calendarDayConfiguration.standardProcessingSchedule.thursday.cutOffTime | HH:mm | No | Order processing cutoff time. Please note that cutoff time is respective of the seller’s time zone. Example: '09:30'(HH:mm) |
| calendarDayConfiguration.standardProcessingSchedule.friday | object | No |  |
| calendarDayConfiguration.standardProcessingSchedule.friday.isWorkingDay | boolean | No | Flag to specify if shipNode is operational on the specified day of each week. Allowed values are true or false. |
| calendarDayConfiguration.standardProcessingSchedule.friday.cutOffTime | HH:mm | No | Order processing cutoff time. Please note that cutoff time is respective of the seller’s time zone. Example: '09:30'(HH:mm) |
| calendarDayConfiguration.standardProcessingSchedule.saturday | object | No |  |
| calendarDayConfiguration.standardProcessingSchedule.saturday.isWorkingDay | boolean | No | Flag to specify if shipNode is operational on the specified day of each week. Allowed values are true or false. |
| calendarDayConfiguration.standardProcessingSchedule.saturday.cutOffTime | HH:mm | No | Order processing cutoff time. Please note that cutoff time is respective of the seller’s time zone. Example: '09:30'(HH:mm) |
| calendarDayConfiguration.additionalDaysOff | array<string> | No | List of additional days on which the fulfillment center is closed. If there are no additional off days, then this list will be empty. Format for Date is ISO 8601. For example: '2021-07-16'(yyyy-MM-dd) |
