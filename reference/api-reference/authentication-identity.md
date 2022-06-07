# Authentication (Identity)

{% hint style="info" %}
**Good to know:** A quick start guide can be good to help folks get up and running with our API in a few steps. Some people prefer diving in with the basics rather than meticulously reading every page of documentation!
{% endhint %}

## Get your Cashew Secret Key (API key)

Your API requests are authenticated using Cashew Secret key. Any request that doesn't include Cashew Secret key will return an error.

You can generate Cashew Secret key from Cashew Merchant Dashboard at any time or Request from Cashew merchant support.

The best way to interact with our API is to use one of our official libraries:

## Authentication

To make your first request, you need to first Authenticate using the Cashew identity API.

{% swagger baseUrl="https://api-dev.cashewpayments.com/v1" method="post" path="/identity/store/authorize" summary="Create and get Cashew Store Token" %}
{% swagger-description %}
Create Store Token
{% endswagger-description %}

{% swagger-parameter in="header" name="Cashewsecretkey" required="true" %}
Cashew Secret Key
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Storeurl" required="true" %}
Merchant Store Base URL
{% endswagger-parameter %}

{% swagger-response status="200" description="Store Token Created" %}
```javascript
{
    "status": "success",
    "message": "Store token created",
    "data": {
        "token": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "expiryTime": "2022-05-26T17:55:34.403"
    }
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="Permission denied" %}
```
{
    "status": "error",
    "message": "Secret key and Store url does not match",
    "errorCode": "401.002.004"
}
```
{% endswagger-response %}
{% endswagger %}

{% hint style="info" %}
**Good to know:** You can use the API Method block to fully document an API method. You can also sync your API blocks with an OpenAPI file or URL to auto-populate them.
{% endhint %}

Take a look at how you might call this method using below code examples:

{% tabs %}
{% tab title="Curl" %}
```javascript
curl 
--location 
--request POST 'https://api.cashewpayments.com/v1/identity/store/authorize' \
--header 'Cashewsecretkey: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx' \
--header 'Storeurl: http://yourstoreurl.com/'
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php

$url = "https://api.cashewpayments.com/v1/identity/store/authorize";

$curl = curl_init($url);
curl_setopt($curl, CURLOPT_URL, $url);
curl_setopt($curl, CURLOPT_POST, true);
curl_setopt($curl, CURLOPT_RETURNTRANSFER, true);

$headers = array(
   "Cashewsecretkey: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
   "Storeurl: http://yourstoreurl.com/",
   "Content-Length: 0",
);
curl_setopt($curl, CURLOPT_HTTPHEADER, $headers);
//for debug only!
curl_setopt($curl, CURLOPT_SSL_VERIFYHOST, false);
curl_setopt($curl, CURLOPT_SSL_VERIFYPEER, false);

$resp = curl_exec($curl);
curl_close($curl);
var_dump($resp);

?>

```
{% endtab %}

{% tab title="Python" %}
```python
import requests
from requests.structures import CaseInsensitiveDict

url = "https://api.cashewpayments.com/v1/identity/store/authorize"

headers = CaseInsensitiveDict()
headers["Cashewsecretkey"] = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
headers["Storeurl"] = "http://yourstoreurl.com/"
headers["Content-Length"] = "0"


resp = requests.post(url, headers=headers)

print(resp.status_code)

```
{% endtab %}

{% tab title="Javascript/Ajax" %}
```javascript
var url = "https://api.cashewpayments.com/v1/identity/store/authorize";

var xhr = new XMLHttpRequest();
xhr.open("POST", url);

xhr.setRequestHeader("Cashewsecretkey", "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx");
xhr.setRequestHeader("Storeurl", "http://yourstoreurl.com/");
xhr.setRequestHeader("Content-Length", "0");

xhr.onreadystatechange = function () {
   if (xhr.readyState === 4) {
      console.log(xhr.status);
      console.log(xhr.responseText);
   }};

xhr.send();
```
{% endtab %}

{% tab title="Java" %}
```java
URL url = new URL("https://api.cashewpayments.com/v1/identity/store/authorize");
HttpURLConnection http = (HttpURLConnection)url.openConnection();
http.setRequestMethod("POST");
http.setDoOutput(true);
http.setRequestProperty("Cashewsecretkey", "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx");
http.setRequestProperty("Storeurl", "http://yourstoreurl.com/");
http.setRequestProperty("Content-Length", "0");

System.out.println(http.getResponseCode() + " " + http.getResponseMessage());
http.disconnect();
```
{% endtab %}

{% tab title="C#/.NET" %}
```csharp
var url = "https://api.cashewpayments.com/v1/identity/store/authorize";

var httpRequest = (HttpWebRequest)WebRequest.Create(url);
httpRequest.Method = "POST";

httpRequest.Headers["Cashewsecretkey"] = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx";
httpRequest.Headers["Storeurl"] = "http://yourstoreurl.com/";
httpRequest.Headers["Content-Length"] = "0";


var httpResponse = (HttpWebResponse)httpRequest.GetResponse();
using (var streamReader = new StreamReader(httpResponse.GetResponseStream()))
{
   var result = streamReader.ReadToEnd();
}

Console.WriteLine(httpResponse.StatusCode);
```
{% endtab %}
{% endtabs %}
