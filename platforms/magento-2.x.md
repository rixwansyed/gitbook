# Magento 2.x

**Please find the integration Details below**

1. Steps –&#x20;

* Download the Plugin [file](https://drive.google.com/file/d/1gzdmO2VyCYJVo3Za5B3ijbYBoYdJb3-k/view?usp=sharing)&#x20;
* unzip the file under Dorcommerce and Place under app/code
* First run - php bin/magento setup:upgrade (Basic env setup)
* php bin/magento setup:di:compile (compile the code)
* php bin/mahento setup:static content deploy -f (install the plugin into magento)
* php bin/magento cache:clean
* php bin/magento cache:flush
* Admin Stores → Configurations → Sales → Payment Methods → Cashew Payment
* Set the Mode to Live Production
* Enter the Cashew Secret **xxxxxxxxxxxxxxxx**
* Save Configuration

2\. After this go to product page and check the widget is there

3\. Set up integration (in Magento) to communicate with REST API

* System > Integration info (new integration)
* include callback URL →  [https://api.cashewpayments.com/v1/stores/magento](https://api-sandbox.cashewpayments.com/v1/stores/magento)
* Identity URL →  [https://api.cashewpayments.com/v1/stores/magento](https://api-sandbox.cashewpayments.com/v1/stores/magento)
* Password → admin login(i.e Magento)
* &#x20;

1. The merchant then needs to go to integration and press activate&#x20;

