Tag :- [[ReadItLater]] , #facebook-api #Google-Sheet #google-App-Script 
Added :- 2023-02-21

-----
# [Import Facebook Ads Data to Google Sheets via Apps Script | Optimization Up](https://optimizationup.com/import-facebook-ads-data-to-google-sheets-via-apps-script/)

There are a few Google Sheets add-ons that allow exporting Facebook Ads reports to Sheets, however, some of them tend to be expensive or lack the support of some new metrics and dimensions. Today, I will walk you through how to get Facebook Ads data to Google Sheets without buying any add-ons and even schedule your reports to run on an ongoing basis.

I built the solution leveraging the Facebook Marketing API and the Google App scripts, it supports all report types and metrics. Follow the steps below to get started.

## 1- Create Facebook App

Navigate to [Facebook for Developers](https://developers.facebook.com/apps/), click ‘***Create App’***, then choose ***‘Manage Business Integrations’***. You will be asked to enter more info like App name and your contact details.

![](https://optimizationup.com/wp-content/uploads/2021/04/image-1-1024x470.jpg)

After you create the app, Navigate your business manager settings, and under Apps click ***‘Add’*** and link your new app to the business manager.

Next, click ***‘Add Assets’*** and select the ad accounts you’d like to pull reports for.

![](https://optimizationup.com/wp-content/uploads/2021/04/image-5-1024x464.jpg)

## 2- Generate your Access Token

Once you create the app, please head to ***Marketing API > Tools*** then select all the 3 token permissions then hit ***‘Get Token’***. Copy and save your token, you will need it in the following steps

![](https://optimizationup.com/wp-content/uploads/2021/04/image-1-1024x342.png)

## 3- Configure your Google App Script

Make a copy of **[this Google Sheet](https://docs.google.com/spreadsheets/d/1daNu5sp8oWg7qUFgRcyb3Lwb3qNWPcPGS_lvK94ewSk/edit#gid=2094008733)**.

![](https://optimizationup.com/wp-content/uploads/2021/04/image-3-1024x576.jpg)

To configure the script, you need to add all your relevant details in the config tab:

**ACCOUNT\_ID**: this should be you ad account ID

**ACCESS\_TOKEN**: this is the access token we generated above from the Facebook App

**START\_DATE**: this should be the start date of your report

**END\_DATE**: this should be the end date of your report

**FIELDS**: This is all the fields you’d like to have in your report like *impressions, clicks, cost..etc*. For all reporting metrics and fields, please see [here](https://developers.facebook.com/docs/marketing-api/insights/parameters#param).

**REPORT\_LEVEL**: this is the level of your report, it could be set to: *ad, adset, campaign, account*

![](https://optimizationup.com/wp-content/uploads/2021/04/image-4-1024x723.png)

Once you are done with your report configuration, you can just click run report, the data should be exported in the FB Ads raw tab.

To schedule the script, click ***Tools > Script Editor***. Inside the script editor click ***‘Triggers’*** then ***‘Add Trigger’***:

![](https://optimizationup.com/wp-content/uploads/2021/04/image-3-1-1024x465.jpg)

Select from the ***‘Choose which function to run’*** dropdown menu downloadReport. The rest of the fields set per your needs, like the type of the time trigger and the actual time.

![](https://optimizationup.com/wp-content/uploads/2021/04/image-3-1024x791.png)

Please try it out and let me know if you have any questions in comments below.

![](https://optimizationup.com/wp-content/uploads/2021/03/Ahmed-Ali-cropped.jpg)

Ex-Google with advanced digital analytics and marketing automation skills. If you are looking for a data-driven professional that will help you save time & money and grow cost-efficiently, you have come to the right person. [**Contact Me!**](https://optimizationup.com/#contact)