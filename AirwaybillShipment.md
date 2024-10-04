## Airwaybill Get Request Documentation
###### This Documentation is about get Rate Request

Live   : `https://api-next.mysoft.web.id/endpoint/transaction/awb/rate_request`

Sandbox: `https://api-next.mysoft.web.id/sandbox/transaction/awb/rate_request`

|Field|Label|Rules|Description|
|-----|-----|-----|-----------|
|awb_next_number|Airwaybill Next Number|M (AN)|Response from Initialize Store New Airwaybill|

## Example Payload Request
```
{
    "awb_next_number": 11123456
}
```

## Success Response
```
{
    "response": [
        {
            "vendor_product_code": "T",
            "delivery_time": "2024-10-09T12:00:00",
            "cutoff_time": "2024-10-07T18:00:00",
            "next_bussiness_day": "Y",
            "surcharges": [
                "EXPRESS 12:00 DOC",
                "12:00 PREMIUM",
                "DEMAND SURCHARGE",
                "FUEL SURCHARGE"
            ]
        },
        {
            "vendor_product_code": "D",
            "delivery_time": "2024-10-09T23:59:00",
            "cutoff_time": "2024-10-07T18:00:00",
            "next_bussiness_day": "Y",
            "surcharges": [
                "EXPRESS WORLDWIDE DOC",
                "DEMAND SURCHARGE",
                "FUEL SURCHARGE"
            ]
        }
    ],
    "status": 200
}
```

## Airwaybill Set Request Documentation
###### This Documentation is about finalizing Airrwaybill that ready to ship

Live   : `https://api-next.mysoft.web.id/endpoint/transaction/awb/shipment_request`

Sandbox: `https://api-next.mysoft.web.id/sandbox/transaction/awb/shipment_request`

|Field|Label|Rules|Description|
|-----|-----|-----|-----------|
|awb_next_number|Airwaybill Next Number|M (AN)|Response from Initialize Store New Airwaybill|
|vendor_product_code|Product Code|M (AN1)|Fetch this from Success Response vendor_product_code|

## Example Payload Request
```
{
    "awb_next_number": 11123456,
    "vendor_product_code": "D"
}
```

## Success Response
```
{
    "status": 200,
    "response": "Airwaybill Ready to Ship",
    "airwaybill": // returning base64 encoded NEXT Airwaybill
}
```
