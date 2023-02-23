Tag :- [[ReadItLater]] , #facebook-api 
Added :- 2023-02-21

-----
# [Facebook Conversion API: A Short and Crisp Guide for Marketers](https://blog.xorlabs.in/marketing-analytics/facebook-conversion-api/)

Pixel-based tracking is NOT the future. All the data about the purchase and purchase conversion value is not accurate any more in your Facebook Ads dashboard.

I am running a campaign for a US client and this is how the sales in Facebook Ads Manager and Shopify Store dashboard (from Facebook & Instagram) compare against each other.

![](Well%20Wallet/ReadItLater%20Inbox/assets/facebook-vs-shopify-sales-dashboard-facebook-conversion-api-1536x603-1-1024x402.jpg..jpg)

That’s a huge difference. While Facebook Ads Manager is telling me that we generated sales of around $1,308.38, the total sales from Facebook & Instagram were $2,156.93.

The reason is the **iOS’14 update**.

iOS’14 has enabled users to take control over the data—that is, they now have to opt-in for apps to track them. Hence, Apple devices are not reporting about conversions meaning a significant amount of purchases through iOS devices are not picked up by Pixel anymore. The effect will be more pronounced when Google takes away third-party tracking from Chrome browsers.

This will have a twofold impact on your ad campaigns:

-   You won’t be able to measure and track all conversions
-   And since you can’t measure, you cannot optimize your campaigns anymore.

However, Facebook Ads has come up with a solution that allows you to solve this tracking problem: It’s called Facebook Conversion API.

## What is a Facebook Conversion API and How does it Work?

Here’s how Facebook defines it:

> ***Conversions API is a Facebook Business tool that lets you share key web and offline events, or customer actions, directly from your server to Facebook’s. Conversions API works with your Facebook pixel to help improve the performance and measurement of your Facebook ad campaigns.***

This is different from how Facebook Pixel works. With Facebook Pixel, when a user enters your website using a browser, it’s the browser that sends events (product views, adds to cart, purchases, etc) to Facebook and then to your Ads Manager.

What can conversion tracking in search help you measure? In Facebook Conversion API, however, when a user enters your website after clicking a Facebook ad, he is assigned a unique ID. This ID allows Facebook to track users’ actions on the website and sent the data from the webserver. When a user makes an activity, for instance, a purchase, that data is sent to Facebook from your web server itself by Facebook APIs.

However, Facebook Pixel is NOT completely dead.

The best practice while setting up conversion API is to link conversion API along with Facebook Pixel.

Here’s a pictorial description of how Facebook Conversion API and Facebook Pixel both send data to Facebook.

![facebook conversion api](Well%20Wallet/ReadItLater%20Inbox/assets/facebook%20conversion%20api..png)

Right now, both Facebook Pixel and Conversion API send data to Facebook. In case, the same is reported to Facebook from both the mechanisms, the data is deduplicated and the browser event is prioritized. 

You need not worry about the same event being counted twice to mess up your data. [Facebook implements easy data deduplication](https://blog.xorlabs.in/marketing-analytics/facebook-conversion-api-data-deduplication/).

Since Facebook Conversion API is not dependent on cookies, so web browser settings don’t impact your ability to track user events. When marketing Facebook API and Pixel are used together, you get more reliable data and the ability to optimize campaigns.

Facebook also offers:

-   Offline Conversions API: To track and measure in-store sales
-   App Events API: To track in-app events, and

Advanced Matching: To attribute more conversions from Facebook

## How to set up Facebook Conversion API

There are two ways in which you can set up tracking using Conversion API

1.  Manual setup (using code—requires a developer)
2.  Partner integration (integration tools)

### Using Manual Setup

Facebook for Developers offers [developer documentation](https://developers.facebook.com/docs/marketing-api/conversions-api) that you can use to set up conversion API on your website. If you want to create more personalized setup instructions, you can find them in Events Manager.

Pros of the manual setup of Facebook APIs

-   The manual setup gives you control over how you set up the Conversions API. That means more control over what you want to track and measure. It also allows you to add customizations as you want
-   Using the manual setup, you can even send events and data that Facebook Pixel doesn’t capture in browsers
-   Since there’s a developer involved, you will need someone to maintain the code, especially when you make big changes and improvements to the website

Cons of the manual setup of Facebook APIs

-   You will need to give access to your server codebase to the developer. So, naturally, you either need someone in-house or an agency that you can trust
-   You will get an additional activity to set up and manage [customer information parameters](https://developers.facebook.com/docs/marketing-api/conversions-api/parameters/customer-information-parameters). For instance, email, phone, gender, name, city, etc.

### Using Partner Integration to link conversion API

All you need to do is use a Facebook Partner Integration tool. You can find the [complete list of Facebook Partners who are providing Conversion API integration for the web](https://www.facebook.com/business/help/260370078559247).

Advantages of using Partner Integration of Facebook APIs

-   This method is simple and fast.
-   That means, minimal development resources are required and you can even ask the Facebook Partner to set it up for you at minimal charges.
-   Most of these partner solutions enable you to integrate data with multiple sources, allowing you to enable cross-channel integration

Disadvantages of using Partner Integration of Facebook APIs

-   Usually, the difference in cost and event availability varies from partner to partner. This also demands that you take time and be careful in comparing multiple partner solutions.
-   Partner solutions also give you lesser control and customizations as compared to manual setup.

### **Conclusion**

Iterating from the example from the top, setting up Facebook Conversion API along with Facebook Pixel means that the marketing team has better data to analyze. As a result, they were able to make better decisions about how to spend their advertising money.

We discovered that combining the pixel with the conversions API resulted in a 40% percent boost in attribution.

This directly impacts ad targeting. Using the conversions API’s additional data helped the Facebook algorithm display advertisements more effectively to better-qualified users, lowering the cost per action significantly.