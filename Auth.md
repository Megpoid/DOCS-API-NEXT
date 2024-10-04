## Authentication Header Configuration
###### This Documentation is about Set Authentication to Header Request

## Example
###### JQUERY AJAX Example
```
var auth = btoa('Basic ' + username + ':' + password)
var settings = {
  "url": "https://api-next.mysoft.web.id/sandbox/transaction/awb/items/store",
  "method": "POST",
  "timeout": 0,
  "headers": {
    "Content-Type": "application/json",
    "Authorization": auth
  },
  "data": JSON.stringify({
    "awb_next_number": 888036704,
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
  }),
};
```