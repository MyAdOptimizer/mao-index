<p align="center">
  <a href="https://myadoptimizer.com/">
    <img src="https://myadoptimizer.com/img/logo-blk.svg" alt="Logo" height="80">
  </a>
  <h3 align="center">MyAdOptimizer.com Server API Integration Doc | Medicare</h3>
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
    * [Specific Query String Parameters for Medicare](#specific-query-string-parameters-for-medicare)
    * [API Response](#api-response)
* [External Ad Networks Setup (OPTIONAL)](#external-ad-networks-setup-optional)

## Server Side

### Request for Server Side

Endpoint [https://api.myadoptimizer.com/api/MAOListingsServerAPI](https://api.myadoptimizer.com/api/MAOListingsServerAPI)

HttpMethod: GET

Response Format: JSON

Generic Query String Parameters

* **LandingPageToken:** This Token will be provided by your account manager
* **Device:** Desktop o Mobile
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


<h3>Specific Query String Parameters for <strong>Medicare</strong></h3>

| Query String Params Names | Data Type | Allowed Values |
| :------------------------ | :-------: | :------------- |
| ZipCode            | string | 5 char US zip code              |
| State*              | string | 2 char US state code (Uppercase) |
| CurrentlyEnrolled*  | string | Yes, No |
| Gender*             | string | Male, Female |
| MilitaryStatus*     | string | Yes, No |
| PreCondition*       | string | Yes, No |
| TobaccoUse*         | string | Yes, No |
| Age                | integer | 1 - 99.  NOTE: If you wish to separate consumers who are >64.5 "Aging in" traffic from consumers who are <64.5 you'll need to collect DOB and use it to determine eligibility.  You can then pass consumers who are >64.5 as "65" and consumers who are <64.5 as "64". |
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

* **impressionUrl:** This is a call back URL so that MAO can track live impressions. If a listing is displayed in your result set, please trigger the impressionUrl of  that listing.

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
    "searchResultId": "5567f49b-6ff4-4895-a275-011d3f05a289",
    "duration": 105,
    "items": [
        {
            "itemId": "229",
            "brandName": "HealthPlanRates",
            "networkSort": 1,
            "requestDuration": 103,
            "sourceID": null,
            "extClickID": null,
            "advertiserId": "152",
            "advertiserName": "Spring Venture Group - 470",
            "displayName": "2020 Health Plans from $59/mo",
            "headline": "See Instant Rate Comparison<br />Compare Affordable Coverage Online <br />Choose from PPO, HMO, & Short Term Plans<br />Top Rated Plans for Families & Individuals",
            "blurbs": [
                "See Instant Rate Comparison",
                "Compare Affordable Coverage Online ",
                "Choose from PPO, HMO, & Short Term Plans",
                "Top Rated Plans for Families & Individuals"
            ],
            "imageUrl": "https://cdn.myadoptimizer.com/maojsfiles/images/LogoAdvertiser_000000_6397b505-02ab-4986-967b-237fb9608fd6.JPG",
            "destUrl": "https://api.myadoptimizer.com/api/MAOHttpRedirect?src=https%3A%2F%2Finfo.floridacareercollege.com%2Fbusiness-office-administration%2F%3Fadkey%3DIS1CAEXN00%26ctc%3D877-425-6149%26utm_source%3Dcexplorer%26utm_medium%3Dcpc%26utm_campaign060118-fcc-cpc%26utm_content%3DFCC-Business%26CCK%3Dacbb214a-e69e-4394-bea0-3b48f6997cca%7Cfcc_business%26t%3DtestClickID&LandingPageID=43&EventID=acbb214a-e69e-4394-bea0-3b48f6997cca&AdNetworkAPIID=44&cpc=7.50&Brand=Florida Career College&Title=Earn A Business Office Administration Diploma - Start Building A Future You Can Be Proud Of&CB=1VawjEjip8ij5oaSZJZ0mw==&M=4XarSvqYDCayCqZpzLZFSg==&Weight=7.50&BidModifiers=50.00&NetworkAdID=458&SourceID=&LandingPageURL=",
            "impressionUrl": "https://api.myadoptimizer.com/api/MAOSaveResults?LandingPageID=43&AdNetworkAPIID=44&EventID=acbb214a-e69e-4394-bea0-3b48f6997cca&AdCampaignID=458&RequestTypeID=4",
             "displayUrl": "http://www.floridacareercollege.com/business-office-administration",
            "revenue": 7.50,
            "baseRevenue" : 5.00,
            "bidModifierLog": [
              "Gender: Female - Value: 50.00%",
              "States: CA - Value: -10.00%",
              "Tuesday: 14:18 - Value: 10.00%"
            ],
            "weight": 7.50,
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
