---
title: "Download Publishing Profile is disabled / Grayed in Azure App Services"
date: 2024-01-24T22:00:00-04:00
categories:
  - blog
tags:
  - Jekyll
  - App Services
  - Azure
---

Is deployment credentials button is disabled or grayed out in your Azure App Services like shown below?

<img src="{{ site.url }}{{ site.baseurl }}/assets/images/1.png" alt="" class="full">

There are couple of ways to download or reset Publishing credentails. 

**Azure Portal:**

If Download deployment credentials, reset deployment credentials are grayed out in your App Service then please follow below process to enable them. 

**Solution:** 
Enable Basic Auth Publishing Credentials Option by navigating to App Service -> Configuration -> General Settings -> Basic Auth Publishing Credentials -> Turn ON. 
{: .notice--primary}

<img src="{{ site.url }}{{ site.baseurl }}/assets/images/2.png" alt="" class="full">

<div class="notice">
  <h8>Note:</h8>
  <p>(If it is already turned on, then please Turn off and Turn ON again. make sure to save for each action and refresh browser page to reflect Download deployment credentials, reset deployment credentials buttons get enabled).</p>
</div>

Once button is enabled, you can download deployment credentials or reset as per your need. 

<img src="{{ site.url }}{{ site.baseurl }}/assets/images/3.png" alt="" class="full">

**CLI or Cloud Shell:**

Cloud Shell can be launched from Azure portal.
Click on the box  with >- on top right corner. Please reference below image (in case if you are using Cloud Shell first time). You need to have permissions to create a storage account, if this is the first time Cloud shell is launched. 

<img src="{{ site.url }}{{ site.baseurl }}/assets/images/4.png" alt="" class="full">

Use below Azure CLI commands to retrive Deployment credentails. 

```
az webapp deployment list-publishing-credentials --name  AppServiceName --resource-group ResourceGroupName
```

Note: Replace AppServiceName and ResourceGroupName in above command with your respective values. 

<img src="{{ site.url }}{{ site.baseurl }}/assets/images/5.png" alt="" class="full">

Check out [Azure CLI Command][reference-url] for additional information. 
Complete [Deployment related CLI commands][fulldep-url] 



[reference-url]: https://learn.microsoft.com/en-us/cli/azure/webapp/deployment?view=azure-cli-latest#az-webapp-deployment-list-publishing-credentials
[fulldep-url]:   https://learn.microsoft.com/en-us/cli/azure/webapp/deployment?view=azure-cli-latest#az-webapp-deployment-list-publishing-credentials

