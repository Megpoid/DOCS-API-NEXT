## Airwaybill Documentation
###### This Documentation is about request payload for initial creating airwaybill

Live   : `https://api-next.mysoft.web.id/endpoint/transaction/awb/store`

Sandbox: `https://api-next.mysoft.web.id/sandbox/transaction/awb/store`

|Field|Label|Rules|Description|
|-----|-----|-----|-----------|
|receiver.name|Receiver Name|M (AN100)||
|receiver.company|Receiver Company|M (AN100)||
|receiver.country_iso_2|Receiver Country ISO-2 Code|M (A2)|[See List](https://api-next.mysoft.web.id/list/iso-2/)|
|receiver.address|Receiver Main Address|M (AN250)||
|receiver.address_2|Receiver Secondary Address|O (AN45)||
|receiver.address_3|Receiver Tertiary Address|O (AN45)||
|receiver.postcode|Receiver Postal Code or Suburb|M (AN50)||
|receiver.city|Receiver City|M (AN50)||
|receiver.state|Receiver State|O (AN50)||
|receiver.email_address|Receiver Email Address|O (AN45)||
|receiver.phone_type|Receiver Phone Type|O (MOBILE,OFFICE,FAX,OTHER)|Select only One|
|receiver.phone_code|Receiver Phone Code|M (N5)|Ex. 62|
|receiver.phone_number|Receiver Phone Number|M (N20)||
|receiver.phone_ext|Receiver Phone Ext|O (N5)||

|Field|Label|Rules|Description|
|-----|-----|-----|-----------|
|shipper.name|Shipper Name|M (AN100)||
|shipper.company|Shipper Company|M (AN100)||
|shipper.country_iso_2|Shipper Country ISO-2 Code|M (A2)|[See List](https://api-next.mysoft.web.id/list/iso-2/)|
|shipper.address|Shipper Main Address|M (AN250)||
|shipper.address_2|Shipper Secondary Address|O (AN45)||
|shipper.address_3|Shipper Tertiary Address|O (AN45)||
|shipper.postcode|Shipper Postal Code or Suburb|M (AN50)||
|shipper.city|Shipper City|M (AN50)||
|shipper.state|Shipper State|O (AN50)||
|shipper.email_address|Shipper Email Address|O (AN45)||
|shipper.phone_type|Shipper Phone Type|O (MOBILE,OFFICE,FAX,OTHER)|Select only One|
|shipper.phone_code|Shipper Phone Code|M (N5)|Ex. 62|
|shipper.phone_number|Shipper Phone Number|M (N20)||
|shipper.phone_ext|Shipper Phone Ext|O (N5)||
|shipper.identification_type|Shipper ID Type|M (PAS,VAT,NID,DLI)|tr, Passport, VAT Registration, National Identity Card, Driver License|
|shipper.identification_number|Shipper ID Number|M (AN100)||
|shipper.account_number|Shipper Account Number|M (AN255)||

|Field|Label|Rules|Description|
|-----|-----|-----|-----------|
|awb_vendor_number|Airwaybill Vendor Number|O (AN100)|Your Custom Airwaybill Number|
|content_type|Content Type|M (DOCUMENTS,NON_DOCUMENTS)|Select One|
|payment_type|Payment Type|M (PREPAID,COLLECT)||
|delivery_date|Delivery Date|Date Format DDDD-MM-YY HH:II|Ex, 31-12-2020 23:30|
|term_of_trade|Term Of Trade|M (N3)|[See List](https://api-next.mysoft.web.id/list/term_of_trades/)|
|shipment_reference|Shipment Reference|O (AN35)||


## Example Payload Request
```
{
  "receiver": {
    "name": "John Doe",
    "bussines_contact": "",
    "company": "Receiver Company",
    "country_iso_2": "US",
    "address": "123 Main St",
    "address_2": "",
    "address_3": "",
    "postcode": "90210",
    "city": "Los Angeles",
    "state": "",
    "email_address": "john.doe@example.com",
    "phone_type": "MOBILE",
    "phone_code": 1,
    "phone_number": 1234567890,
    "phone_ext": ""
  },
  "shipper": {
    "name": "Shipper Name",
    "bussines_contact": "",
    "company": "Shipper Company",
    "country_iso_2": "ID",
    "address": "789 Shipper St",
    "address_2": "",
    "address_3": "",
    "postcode": "12780",
    "city": "Jakarta",
    "state": "",
    "email_address": "shipper@example.com",
    "phone_type": "OFFICE",
    "phone_code": 1,
    "phone_number": 9876543210,
    "phone_ext": "",
    "identification_type": "PAS",
    "identification_number": "123456789",
    "account_number": "SH123456789"
  },
  "awb_vendor_number": "AWB123456",
  "content_type": "DOCUMENTS",
  "payment_type": "PREPAID",
  "delivery_date": "2024-10-05 23:30",
  "term_of_trade": "CFR",
  "shipment_reference": "Lorem Ipsum Dolor"
}
```

## Success Response
```
{
    "status": "success",
    "message": "Airwaybill has been stored",
    "awb_next_number": 11123456
}
```
