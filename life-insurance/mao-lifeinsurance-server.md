<p align="center">
  <a href="https://myadoptimizer.com/">
    <img src="https://myadoptimizer.com/img/logo-blk.svg" alt="Logo" height="80">
  </a>
  <h3 align="center">MyAdOptimizer.com Server API Integration Doc | Life Insurance</h3>
  <p align="center">
    Learn how to integrate the <strong>MAO Server API</strong> by following these steps
    <br />
    <a href="https://myadoptimizer.com">View Site</a>
    ·
    <a href="https://myadoptimizer.com/contact">Report Bug</a>
  </p>
</p>

## Table of Contents

* [Server Side](#server-side)
    * [Request for Server Side](#request-for-server-side)
    * [Specific Query String Parameters for Life Insurance](#specific-query-string-parameters-for-life-insurance)
    * [API Response](#api-response)
* [External Ad Networks Setup (OPTIONAL)](#external-ad-networks-setup-optional)

## Server Side

### Request for Server Side

Endpoint [https://api.myadoptimizer.com/api/MAOListingsServerAPI](https://api.myadoptimizer.com/api/MAOListingsServerAPI)

HttpMethod: GET

Response Format: JSON

Generic Query String Parameters

* **LandingPageToken:** This Token will be provided by your account manager
* **Device:** Desktop or Mobile. Some 3rd Party AdNetworks or Private Exchange Campaigns might require this value to be provided when using Server Side integration
* **ClientIP:** This is the user's IP
* **CurrentURL:** Optional, the URL where listings will be displayed
* **SourceID:** Optional, tracking variable

* **ExtClickID:** Optional, tracking variable
> [!NOTE]
> This tracking variables requires special integration. You need to append it to the destURL property from the results returned by API call.

* **UserAgent:** Optional,  Mozilla/<version> (<system-information>) <platform> (<platform-details>) <extensions>
* **CustomVar1:** Optional, tracking variable (Max length - 75)
* **CustomVar2:** Optional, tracking variable (Max length - 75)
* **CustomVar3:** Optional, tracking variable (Max length - 75)
* **CustomVar4:** Optional, tracking variable (Max length - 75)
* **CustomVar5:** Optional, tracking variable (Max length - 75)


<h3>Specific Query String Parameters for <strong>Life Insurance</strong></h3>

| Query String Params Names | Data Type | Allowed Values |
| :------------------------ | :-------: | :------------- |
| ZipCode            | string | 5 char US zip code              |
| State*              | string | 2 char US state code (Uppercase) |
| CurrentPolicy*  | string | Yes, No |
| EmploymentStatus*    | string |  Employed, Self-Employed, Retired, Not Employed       |
|CoverageAmount | int | 0 - 5000000 |
|InsuranceType | string | Term, Whole, Final Expense |
| Gender*             | string | Male, Female |
| MilitaryStatus*     | string | Yes, No |
| Married*                   | string | Married, Single |
| PreCondition*       | string | Yes, No |
| TobaccoUse*         | string | Yes, No |
| Age                | integer | 1 - 99 |
| MediaChannel                | string    | Social, Facebook, Native, Email, Display, SEM, SEO, SMS, Push, Affiliate, ChannelA, ChannelB, ChannelC, ChannelD, ChannelE |
| FName ±                    | string    |  |
| LName ±                    | string    |  |
| Email ±                    | string    |  |
| Phone ±                    | string    |  |
| Address ±                  | string    |  |
| City ±                     | string    |  |

*Case Sensitive

±PII Fields

### API Response


* **destURL:** This is the Click URL. Please use the value from this field when a click is triggered.

* **impressionUrl:** In the event that you are not planning to render all listings returned by this API you need to use this trigger. This is a call back URL to track live impressions. If a listing is displayed in your result set, please trigger the impressionUrl of that listing.

* **displayUrl:** This is the value from “Display URL” in the Campaign Ad Copy. 

* **trackingURL:** This is a Image Pixel to track leads or form submits from Clicks. This is optional to implement, but it is used to provide traceability from a click to a lead submit.

* **revenue:** Actual payout per click based on bid modifiers.

* **baseRevenue:** Base bid per click. It'll vary based on bid modifiers.

* **bidModifierLog:** The log that shows  how the baseRevenue bid was modified.

* **advertiserName:** The name of the advertiser - The ID of the advertiser

* **campaignPhoneNumber:** `New!` A unique phone number assigned to the campaign to track and measure calls.

* **callToAction:** `New!` Text displayed on a clickable button or element, encouraging users to initiate a phone call.

* **adResultCallStatusID:** `New!` An ID representing the campaign's call status, where:

| ID | Status                           | Allows calls |
| :--| :------------------------------- | :------------|
|1   | Click To Call is Active          | TRUE         |  
|8   | Campaign is out of schedule      | FALSE        |
|13  | Click to Call Monthly Cap Reached| FALSE        |
|14  | Click to Call Daily Cap reached  | FALSE        |
|15  | Click to Call is Off             | FALSE        |
|16  | Campaign is off                  | FALSE        |

> [!NOTE]
> When the campaign is inactive, the following message is broadcast: I'm sorry, but our campaign is currently inactive. Please try again later

Example response:
 ```javascript
{
    "searchResultId": "e7eadf56-87b3-41a2-8c05-457523caf2a0",
    "duration": 869,
    "items": [
        {
            "itemId": "181",
            "brandName": "Provide Insurance",
            "networkSort": 1,
            "requestDuration": 666,
            "sourceID": null,
            "extClickID": null,
            "advertiserId": "111",
            "advertiserName": "TruStage - 970",
            "displayName": "Get Better Home Insurance Rates!",
            "headline": "Homeowners are shocked at this Genius Tip &lt;br /&gt;Compare 3+ Rates at Once for Max Savings!&lt;br /&gt;See if you Qualify for Lower Home Insurance&lt;br /&gt;Save Today with a Fast Free Quote!",
            "blurbs": [
                "Homeowners are shocked at this Genius Tip ",
                "Compare 3+ Rates at Once for Max Savings!",
                "See if you Qualify for Lower Home Insurance",
                "Save Today with a Fast Free Quote!"
            ],
            "imageUrl": "https://cdn.myadoptimizer.com/maojsfiles/images/LogoAdvertiser_000000_fd8c4c64-6015-4720-91a8-9b359c754666.JPG",
            "destUrl": "https://api.myadoptimizer.com/api/MAOHttpRedirect?src=https://provide-homeowners-savings.com/&LandingPageID=20&EventID=e7eadf56-87b3-41a2-8c05-457523caf2a0&AdNetworkAPIID=23&cpc=9.75&Brand=Provide Insurance&Title=Get Better Home Insurance Rates!&CB=MxI+ul0svmqhIc6i55uEoA==&M=4XarSvqYDCayCqZpzLZFSg==&Weight=9.75&BidModifiers=50.00&NetworkAdID=181&SourceID=&LandingPageURL=" ,
            "displayURL": "ProvideHomeownersSavings.com/Quotes"
            "impressionUrl": "https://api.myadoptimizer.com/api/MAOSaveResults?LandingPageID=26&AdNetworkAPIID=29&EventID=ae9540ce-7f31-405e-b21c-f11e7a2168b8&AdCampaignID=311&RequestTypeID=4",
            "revenue": 9.75,
            "baseRevenue": 6.50,
            "bidModifierLog": [
              "Gender: Female - Value: 50%",
              "State: CA - Value: -10%",
              "Tuesday: 14:40 - Value: 10%"
            ],
            "weight": 9.75,
            "statusId": 1,
            "trackingURL": "https://api.myadoptizer.com/api/MAOLeadTracking?AdNetworkAPIID=27&LandingPageID=24&EventID=8b448cc4-da0b-4f70-b180-c0c883282a49&IP=128.1.1.1&AdCampaignID=168",
            "campaignPhoneNumber": "+11234567890",
            "callToAction": "Call Now",
            "adResultCallStatusID": 1
        }
    ]
}
```

## External Ad Networks Setup OPTIONAL

To integrate the following Ad Networks, MAO will need the following values.
```diff
- Please provide YOUR publisher source values for each ad network below.
```
Media Alpha
* `api_token` 
* `placement_id`

Transparent.ly
* `pubcampaignId`

Clicks.NET
* `Affcamid`
* `Key`

Quinstreet
* `Src`
