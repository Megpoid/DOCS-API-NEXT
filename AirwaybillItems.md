## Airwaybill Items Documentation
###### This Documentation is about set items after initialize Airwaybill

Live   : `https://api-next.mysoft.web.id/endpoint/transaction/awb/items/store`

Sandbox: `https://api-next.mysoft.web.id/sandbox/transaction/awb/items/store`

|Field|Label|Rules|Description|
|-----|-----|-----|-----------|
|awb_next_number|Airwaybill Next Number|M (AN)|Response from Initialize Store New Airwaybill|
|items.*.name|Item Name|M (AN170)||
|items.*.manufactur_id|Item Manufacturer|O (AN150)||
|items.*.qty|Item Quantity|M (N Min:1, Max:100)||
|items.*.unit|Item Quantity|Mandatory if content_type is NON_DOCUMENTS|(https://api-next.mysoft.web.id/list/units/)|
|items.*.value|Currency Worth Value of Item|Mandatory if content_type is NON_DOCUMENTS (N)||
|items.*.currency|Item Currency of Value|Mandatory if content_type is NON_DOCUMENTS (A3)|(https://api-next.mysoft.web.id/list/currencies/)|
|items.*.weight|Item Weight|M (A)|Weight Before Packaging|
|items.*.country_iso_2|Item Country Created|M (A2)|[See List](https://api-next.mysoft.web.id/list/iso-2/)|


## Example Payload Request
```
{
    "awb_next_number": 11123456,
    "items": [
        {
            "name": "Foo Bar 1",
            "qty": 1,
            "weight": 12.66,
            "unit": "PCS",
            "value": "2",
            "currency": "USD",
            "country_iso_2": "ID"
        }
    ]
}
```

## Success Response
```
{
    "status": "success",
    "message": "Items has been stored"
}
```

## Airwaybill Packages Documentation
###### This Documentation is about set Packages after initialize Airwaybill

Live   : `https://api-next.mysoft.web.id/endpoint/transaction/awb/packages/store`

Sandbox: `https://api-next.mysoft.web.id/sandbox/transaction/awb/packages/store`

|Field|Label|Rules|Description|
|-----|-----|-----|-----------|
|awb_next_number|Airwaybill Next Number|M (AN)|Response from Initialize Store New Airwaybill|
|packages.*.qty|Package Quantity|M (N Min:1, Max:100)||
|packages.*.weight|Item Weight|M (D)|Format: 0.00, Ex. 1.50|
|packages.*.height|Item Height|M (D)|Format: 0.00, Ex. 1.50|
|packages.*.length|Item Length|M (D)|Format: 0.00, Ex. 1.50|
|packages.*.width|Item Width|M (D)|Format: 0.00, Ex. 1.50|

## Example Payload Request
```
{
    "awb_next_number": 11123456,
    "packages": [
        {
            "qty": 1,
            "weight": 12.66,
            "height": 24.00,
            "length": 5.00,
            "width": 20.00
        },
        {
            "qty": 2,
            "weight": 12.66,
            "height": 24.00,
            "length": 5.00,
            "width": 20.00
        }
    ]
}
```

## Success Response
```
{
    "status": "success",
    "message": "Packages has been stored"
}
```
