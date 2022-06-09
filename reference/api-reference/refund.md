# Refund

{% hint style="info" %}
**Good to know:** All the methods shown below are synced to an example Swagger file URL and are kept up to date automatically with changes to the API.
{% endhint %}

## Submit Refund

{% swagger src="https://api-dev.cashewpayments.com/v1/refunds/v2/api-docs" path="/v1/refunds" method="post" %}
[https://api-dev.cashewpayments.com/v1/refunds/v2/api-docs](https://api-dev.cashewpayments.com/v1/refunds/v2/api-docs)
{% endswagger %}

Take a look at how you might call this method using below code examples:

{% tabs %}
{% tab title="PHP" %}
```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://api-dev.cashewpayments.com/v1/refunds',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_POSTFIELDS =>'{
  "currencyCode": "AED",
  "orderId": 10010000004110,
  "refundAmount": 100,
  "storeId": 100004
}',
  CURLOPT_HTTPHEADER => array(
    'Authorization: xxxxxxxxxxxxxxxxxxxxxxxxxxx'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```


{% endtab %}

{% tab title="CURL" %}
```json
curl --location --request POST 'https://api-dev.cashewpayments.com/v1/refunds' \
--header 'Authorization: eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiI3MDAwMDIyIiwicm9sZSI6IlNUT1JFIiwiaWF0IjoxNjQ4NjI1MTY2LCJleHAiOjE2NDg2Mjg3NjZ9.R0_gub-KP8dlDE73pTMRHT9Tilt87BiXLvTtqxjPg4w' \
--data-raw '{
  "currencyCode": "AED",
  "orderId": 10010000004110,
  "refundAmount": 100,
  "storeId": 100004
}'
```


{% endtab %}

{% tab title="Java Script" %}
```javascript
// WARNING: For POST requests, body is set to null by browsers.
var data = "{\n  \"currencyCode\": \"AED\",\n  \"orderId\": 10010000004110,\n  \"refundAmount\": 100,\n  \"storeId\": 100004\n}";

var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function() {
  if(this.readyState === 4) {
    console.log(this.responseText);
  }
});

xhr.open("POST", "https://api-dev.cashewpayments.com/v1/refunds");
xhr.setRequestHeader("Authorization", "eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiI3MDAwMDIyIiwicm9sZSI6IlNUT1JFIiwiaWF0IjoxNjQ4NjI1MTY2LCJleHAiOjE2NDg2Mjg3NjZ9.R0_gub-KP8dlDE73pTMRHT9Tilt87BiXLvTtqxjPg4w");

xhr.send(data);jss
```


{% endtab %}

{% tab title="Java" %}
```java
OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("text/plain");
RequestBody body = RequestBody.create(mediaType, "{\n  \"currencyCode\": \"AED\",\n  \"orderId\": 10010000004110,\n  \"refundAmount\": 100,\n  \"storeId\": 100004\n}");
Request request = new Request.Builder()
  .url("https://api-dev.cashewpayments.com/v1/refunds")
  .method("POST", body)
  .addHeader("Authorization", "eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiI3MDAwMDIyIiwicm9sZSI6IlNUT1JFIiwiaWF0IjoxNjQ4NjI1MTY2LCJleHAiOjE2NDg2Mjg3NjZ9.R0_gub-KP8dlDE73pTMRHT9Tilt87BiXLvTtqxjPg4w")
  .build();
Response response = client.newCall(request).execute();
```


{% endtab %}
{% endtabs %}
