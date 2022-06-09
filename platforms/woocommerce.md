# WooCommerce

**Wordpress Integration Details**

1. Please download Cashew payments WordPress Plugin from below link

https://drive.google.com/file/d/1Imtuts6HIVoLkDGTdIRsqXtQUKHYmFjE/view?usp=sharing

2\. Upload and activate the plugin

After Activating the plugin, please follow the following steps

* Go to WooCommerce -> Settings -> Payments -> Enable Cashew Payments -> Save&#x20;
* Click on Manage in front of Cashew Payments &#x20;
* Enter the **Cashew Secret** in the Mentioned box&#x20;
* Set Env to **Production** live&#x20;
* Set **Min** Limit to \[your min store limit] and **Max** to \[your max store limit]&#x20;
* Save Settings

3\. Click on REST API &#x20;

* Click Add API&#x20;
* ENTER keys Name  "**Cashew Payments"** and save (Share the keys with us)&#x20;

4\. Click on **Webhooks**&#x20;

* Create new Webhook
* Choose topic Order Created and name it "Order Created"
* ENTER the delivery URL "[https://api.cashewpayments.com/v1/stores/woocommerce](https://api.cashewpayments.com/v1/stores/woocommerce)"
* Set the Status Active
* Set Secret **"Share this Secret with Cashew Payments Integration Team"**
* Click Save

4\. Create New Webhook

* Create new Webhook
* Choose topic Order Updated and name it "Order Updated"
* ENTER the delivery URL "[https://api.cashewpayments.com/v1/stores/woocommerce](https://api.cashewpayments.com/v1/stores/woocommerce)"
* Set the Status Active
* Set Secret **"Share this Secret with Cashew Payments Integration Team"**
* Click Save

