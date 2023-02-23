Tag :- [[ReadItLater]] , #facebook-api 
Added :- 2023-02-21

-----
# [How to automatically pull Facebook Ads data into Spreadsheets](https://medium.com/@nicolashenrypate/how-to-automatically-pull-facebook-ads-data-into-spreadsheets-8418abeabd39)

After seeing how to send your [Google Ads campaign data to Spreadsheets](https://medium.com/@nicolashenrypate/how-to-automatically-pull-google-ads-data-to-spreadsheets-9d38f1b90be0) we will do the same with Facebook Ads. Once again, the idea is to implement a data-driven strategy in campaign performance management. But in my opinion, monthly or even weekly reporting are not enough: it has to be daily. And so that it doesn’t take you 20 minutes a day to export your CSV files and format them, here’s how to automate the boring stuff.

## **Creating an application on Facebook Developer**

In order to access the Facebook API, you need to create an application on Facebook Developer.

1.  Go to the following url : developers.facebook.com
2.  Login with your Facebook account.
3.  Click on ‘Create a Facebook Developer Account’.
4.  Click the “My Applications” tab > “Create an App”.
5.  Give your application a name like “Reporting”.

Now that your application has been created, you need to give it the necessary permissions to access the content you are interested in: reading campaign performance.

6\. In Add a product click on: Set up “API Marketing.

7\. In Marketing API > Tools select “ads\_read” and “read\_insights”.

8\. Click on “Get the token”: you will have a long alphanumeric string that will appear on the screen, don’t share it with anyone, it’s your precious! This tolkien, sorry, this token is the key to authenticate yourself and access the Facebook API. This key is not eternal, it lasts about 2 months. But don’t worry, we’ll see how to manage this limited lifetime so that your script doesn’t stop working overnight.

> “I wish it need not have happened in my time,” said Frodo. “So do I,” said Gandalf, “and so do all who live to see such times. But that is not for them to decide. All we have to decide is what to do with the time that is given us.” ― J.R.R. Tolkien, The Fellowship of the Ring

## Preparing the Spreadsheet

The first step is to prepare the Spreadsheet that will serve as your destination for data import. Open two spreadsheets and name them “Facebook Ads Campaigns” and “Facebook Ads Ad Account” respectively. You can change the names of the sheets, but in this case you will also have to do the same in the script.

Then go to the script editor: “Tools” > “Script Editor”.

## Wrinting the script

The script will depend on the information you want to send to your Spreadsheet. I consider that there are two main components to be defined for automated reporting

-   **Granularity**: what is the focal length with which I want to look at the performance of my campaigns? If it’s a global vision, choose the Ad Account level to get the performance of Facebook Ads, for a more local vision, choose the campaign level.
-   **Updating** or **appending** : updating rows can be useful if you want to create a budget monitoring dashboard that summarizes your campaign’s spendings since the beginning of the month for example. It will squeeze old data and replace it with the new one. If you want to have a daily breakdown of your campaign’s performance, the following method is preferred. It appends new rows to write new data keeping the old one.

In order for you to have both methods I propose a script that :

-   Updates the previous day’s performance of Facebook Ads campaigns on a spreadsheet.
-   Adds a new line with the overall account performance achieved the day before.

This allows you to have both a quick view of the performance of the campaigns and check if there is a problem for one of them while having the performance of the account since the beginning of the month for example.

**Here goes the script :**

**Replace the following information**

Enter your Ad Account Id and the token you obtained in the previous step. Don’t forget the quotation marks !

**Choice of data to be sent**

This script proposes to return the following fields: campaign\_name, impressions, spend, cpc, ctr and cpm. You can of course customize these metrics, here is the list of available fields:

If for example you want to add the metric “clicks” :

-   Add to var urlCampaignInsights :

fields=campaign\_name%2cimpressions%2cspend%2ccpc%2cctr%2ccpm**%2Cclickcs…**

-   Add the variable clicks to collect the requested information :

…  
var ctr = campaignData.ctr  
**var clicks = campaignData.clicks  
**…

-   Finally don’t forget to tell the script to display this information on the spreadsheet :

…  
sheet.getRange(j+2,6).setValue(ctr)  
**sheet.getRange(j+2,7).setValue(clicks)  
**…

If you also want to add a metric in the reporting at the ad account level, consider adding lines of similar code after lines 74, 87 and 97 and also add “2%Cclick” to line 60.

## Manage token expiration date

As we said the token has a life span of two months. So that your script doesn’t stop running overnight, I offer you a script that alerts you by email one week before your token expires. This gives you time to update it.

For this you need to know the SecretClient and the clientId of your application. Go to “Settings” > “General”. You will get your Id and your secret and add it to your script.

And add this script after the previous one in the script editor (don’t forget to add your email adress in the variable *var mailAdress* ) :

When you receive the aleter email, you will just have to connect to Facebook Developer then “Tools” > “API Graph Explorer”. Check that you have selected the right app and then click on “Generate Access Token”. You just have to replace the new token in your script.

## Schedule the script

Now that your script is ready lets schedule it to run periodically and update your dashboard.

1.  Access Google’s script editor click on “Edit” > “Current Projet Triggers”.
2.  Click on “Add Trigger” at the bottom right of the page. Select the funciton “facebookAdsReporting”, choose “Hourly Trigger” in “Select the source of event”, then select “Daily” in “Select the type of time trigger”. Save your trigger.
3.  Now add a new trigger for the function “facebookTokenExpiringAlert” with the same set up.

…you’ve just automatized your Facebook Ads reporting !

I’m not a developer, the code isn’t very elegant but it works fine. Those who have some javascript skills are welcome to improve the code. Hope you enjoy it anyway !