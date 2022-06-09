# Dispatch

{% hint style="info" %}
**Good to know:** All the methods shown below are synced to an example Swagger file URL and are kept up to date automatically with changes to the API.
{% endhint %}

## Dispatch Order

{% swagger src="https://api-dev.cashewpayments.com/v1/orders/v2/api-docs" path="/v1/orders/{orderId}/dispatch" method="post" %}
[https://api-dev.cashewpayments.com/v1/orders/v2/api-docs](https://api-dev.cashewpayments.com/v1/orders/v2/api-docs)
{% endswagger %}

Take a look at how you might call this method using below code examples:

{% tabs %}
{% tab title="PHP" %}
```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://api-dev.cashewpayments.com/v1/stores/magento/dispatch',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_POSTFIELDS =>'{
  "entityId": "12345678",
  "numShippedItems": [
    {
      "qty_shipped": 1,
      "reference": "1234"
    }
  ],
  "orderReference": "396"
}',
  CURLOPT_HTTPHEADER => array(
    'Authorization: xxxxxxxxxxxxxxxxxxx'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;php
```


{% endtab %}

{% tab title="CURL" %}
```php
curl --location --request POST 'https://api-dev.cashewpayments.com/v1/stores/magento/dispatch' \
--header 'Authorization: xxxxxxxxxxxxxxxxxxxxxxx' \
--data-raw '{
  "entityId": "12345678",
  "numShippedItems": [
    {
      "qty_shipped": 1,
      "reference": "1234"
    }
  ],
  "orderReference": "396"
}'
```


{% endtab %}

{% tab title="Java" %}
```java
OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("text/plain");
RequestBody body = RequestBody.create(mediaType, "{\n  \"entityId\": \"12345678\",\n  \"numShippedItems\": [\n    {\n      \"qty_shipped\": 1,\n      \"reference\": \"1234\"\n    }\n  ],\n  \"orderReference\": \"396\"\n}");
Request request = new Request.Builder()
  .url("https://api-dev.cashewpayments.com/v1/stores/magento/dispatch")
  .method("POST", body)
  .addHeader("Authorization", "eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiI3MDAwMDIyIiwicm9sZSI6IlNUT1JFIiwiaWF0IjoxNjQ4MDM2NzY3LCJleHAiOjE2NDgwNDAzNjd9.zmYlwQQS-fSxnuUyaiz6QVPbiyhQqDPlW9fjsPmF8QI")
  .build();
Response response = client.newCall(request).execute();
```


{% endtab %}

{% tab title="Javascript" %}
```javascript
// WARNING: For POST requests, body is set to null by browsers.
var data = "{\n  \"entityId\": \"12345678\",\n  \"numShippedItems\": [\n    {\n      \"qty_shipped\": 1,\n      \"reference\": \"1234\"\n    }\n  ],\n  \"orderReference\": \"396\"\n}";

var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function() {
  if(this.readyState === 4) {
    console.log(this.responseText);
  }
});

xhr.open("POST", "https://api-dev.cashewpayments.com/v1/stores/magento/dispatch");
xhr.setRequestHeader("Authorization", "eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiI3MDAwMDIyIiwicm9sZSI6IlNUT1JFIiwiaWF0IjoxNjQ4MDM2NzY3LCJleHAiOjE2NDgwNDAzNjd9.zmYlwQQS-fSxnuUyaiz6QVPbiyhQqDPlW9fjsPmF8QI");

xhr.send(data);
```


{% endtab %}
{% endtabs %}
