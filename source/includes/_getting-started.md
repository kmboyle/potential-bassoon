# Getting Started

## Ping
If this call fails, API credentials are questionable.

Our PING API is typically used to ensure API credentials are valid, and to ensure the networking "stack" between your systems and TaxCloud's systems are configured correctly to accommodate real-time communications.


```shell
curl "https://api.taxcloud.net/1.0/TaxCloud/Ping"
```

<!-- ```csharp
const req = '';
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
``` -->

> Example Request Body

```json
{
    "apiKey": "string",
    "apiLoginID": "string"
}
```

### HTTP Request

`POST https://api.taxcloud.net/1.0/TaxCloud/Ping`

### Properties

Name | Type | Description
--------- | ------- | -----------
apiKey | string | Find your API KEY via your <a href="https://taxcloud.com/go/stores/" target="_blank">store</a>
apiLoginID | string | Find your API ID via your <a href="https://taxcloud.com/go/stores/" target="_blank">store</a>

> The above command returns JSON structured like this:

```json
{
    "Messages": [
        "string"
    ],
    "ResponseType": "int32"
}
```

### Response

The following HTTP status codes may be returned, optionally with a response resource.

Status code | Description | Resource
--------- | ------- | -----------
200 | OK | PingResponse

### PingResponse Resource Properties

Name | Type | Description | Additional
--------- | ------- | ----------- | ----------
Messages[] | array of string | Optional array of messages related to the response. | Optional
ResponseType | int32 | Response Type includes: <ul><li>0 = Error. likely invalid credentials</li><li>1 = Warning.  Something went wrong.</li><li>2 = Informational. Something could be better</li><li>3 = Success!  You did it!</li>                                   | Optional


<!-- <aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside> -->


## Verify Address
Verify (hopefully improve) a customer provided delivery address. **VERY IMPORTANT** for proper tax jurisdiction assessment.

If you use a domestic common carrier (shipper), you may already have address verification implemented and available. However, if you are not already performing address verification sufficient to determine the a complete 9-digit zip code (e.g., 06851-5715) then our VerifyAddress can fill that gap.

Please see our helpful guide: How to Verify and Address (and Why) for more information.


<aside class="notice">
<strong>IMPORTANT</strong>: If VerifyAddress fails for any reason, you should proceed to Lookup using the customer-provided information.
</aside>


```shell
curl "https://api.taxcloud.net/1.0/TaxCloud/VerifyAddress"
```

```csharp
const req = '';
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> Example Request Body

```json
{
    "Address1": "string",
    "Address2": "string",
    "City": "string",
    "State": "string",
    "Zip4": "number",
    "Zip5": "number",
    "apiKey": "string",
    "apiLoginID": "string"
}
```

### HTTP Request

`POST https://api.taxcloud.net/1.0/TaxCloud/VerifyAddress`

### Properties

Name | Type | Description | Additional
--------- | ------- | ----------- | -----------
Address1 | string |               | 
Address2 | string |               | Optional
City | string |                   |
State | string |                  |
Zip4 | string |                   | Optional
Zip5 | string |                   | Optional
apiKey | string | Find your API KEY via your <a href="https://taxcloud.com/go/stores/" target="_blank">store</a>
apiLoginID | string | Find your API ID via your <a href="https://taxcloud.com/go/stores/" target="_blank">store</a>

> The above command returns JSON structured like this:

```json
{
    "VerifyAddressResult": {
        "Address1": "string",
        "Address2": "string",
        "City": "string",
        "ErrDescription": "string",
        "ErrNumber": "string",
        "State": "string",
        "Zip4": "string",
        "Zip5": "string"
    }
}
```

### Response

The following HTTP status codes may be returned, optionally with a response resource.

Status code | Description | Resource
--------- | ------- | -----------
200 | OK | VerifyAddressResponse

### VerifyAddressResponse Resource Properties

Name | Type | Description | Additional
--------- | ------- | ----------- | ----------
VerifyAddressResult |	object |	  |	Optional
VerifyAddressResult.Address1 |	string	|	| Optional
VerifyAddressResult.Address2 |	string	|	| Optional
VerifyAddressResult.City |	string |		| Optional
VerifyAddressResult.ErrDescription |	string	 | If null, there were no errors. | Optional
VerifyAddressResult.ErrNumber |	string | Our response for VerifyAddress is a little odd. If ErrNumber is "0" then there was no error, and ErrDescription will be null. **IMORTANT** Even if there are errors (the address couldn't be validated/improved) **YOU SHOULD PROCEED WITH THE CUSTOMER PROVIDED ADDRESS.** | Optional
VerifyAddressResult.State |	string  |	 |  Optional
VerifyAddressResult.Zip4  |	string	|	 |  Optional
VerifyAddressResult.Zip5  |	string	|	 |  Optional


<!-- <aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside> -->

## Lookup



## Authorized with Capture

## Returned 

