<p align="center">
  <a href="https://myadoptimizer.com/">
    <img src="https://myadoptimizer.com/img/logo-blk.svg" alt="Logo" height="80">
  </a>
  <h3 align="center">MyAdOptimizer.com Server API Integration Doc | Purchase</h3>
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
    * [Specific Query String Parameters for Purchase](#specific-query-string-parameters-for-mortgage-purchase)
    * [API Response](#api-response)
* [External Ad Networks Setup (OPTIONAL)](#external-ad-networks-setup-optional)

## Server Side

### Request for Server Side

Endpoint [https://api.myadoptimizer.com/api/MAOListingsServerAPI](https://api.myadoptimizer.com/api/MAOListingsServerAPI)

HttpMethod: GET

Response Format: JSON

Generic Query String Parameters

* LandingPageToken: `This Token will be provided by your account manager`
* Device: `Desktop o Mobile`
* ClientIP: `This is the user's IP`
* CurrentURL: `Optional, the URL where listings will be displayed`
* SourceID: `Optional, tracking variable`
* ExtClickID: `Optional, tracking variable`
* UserAgent: `Optional,  Mozilla/<version> (<system-information>) <platform> (<platform-details>) <extensions>`


<h3>Specific Query String Parameters for <strong>Purchase</strong></h3>

| Query String Params Names | Data Type | Allowed Values |
| :------------------------ | :-------: | :------------- |
| ZipCode         | string  |  5 char US zip code              |
| State*           | string  | 2 char US state code (Uppercase)  |
| creditscore*     | string  | Excellent, Good, Fair, Poor |
| loanbalance     | int  |    0-10000000                         |
| propertyvalue   | int  |     0-10000000                        |
| MediaChannel*                | string    | Social, Facebook, Native, Email, Display, SEM, SEO, SMS, Push, Affiliate, ChannelA, ChannelB, ChannelC, ChannelD, ChannelE |
| MilitaryStatus* | string  | Yes, No |
| EmploymentStatus*    | string |  Employed, Self-Employed, Retired, Not Employed       |
| firsttimebuyer*     | string  | Yes, No |
| FName ±                    | string    |  |
| LName ±                    | string    |  |
| Email ±                    | string    |  |
| Phone ±                    | string    |  |
| Address ±                  | string    |  |
| City ±                     | string    |  |

*Case Sensitive

±PII Fields

### API Response

* destURL: `This is the Click URL. Please use the value from this field when a click is triggered.`
* impressionUrl: `This is a call back URL so that MAO can track live impressions. If a listing is displayed in your result set, please trigger the impressionUrl of  that listing`
* displayUrl: `This is the value from “Display URL” in the Campaign Ad Copy `
* trackingURL: `This is a Image Pixel to track leads or form submits from Clicks. This is optional to implement, but it is used to provide traceability from a click to a lead submit`
* revenue: `Actual payout per click based on bid modifiers.`
* baseRevenue: `Base bid per click. It'll vary based on bid modifiers.`
* bidModifierLog: `The log that shows  how the baseRevenue bid was modified.`

Example response:
 ```javascript
{
    "searchResultId": "724829af-612a-44a7-befc-fcbede540c28",
    "duration": 853,
    "items": [
        {
            "itemId": "131",
            "brandName": "Rate Chopper",
            "networkSort": 1,
            "requestDuration": 679,
            "sourceID": null,
            "extClickID": null,
            "advertiserId": "34",
            "displayName": "Save On Your Mortgage Today",
            "headline": "Get Offers Customized Only to You From 2.14% APR&lt;br /&gt;Take Advantage of Historic Low Rates. Can&#39;t Hurt to Look&lt;br /&gt;Hundreds of Lenders Available&lt;br /&gt;Only Takes 2 Minutes to Check",
            "blurbs": [
                "Get Offers Customized Only to You From 2.14% APR",
                "Take Advantage of Historic Low Rates. Can't Hurt to Look",
                "Hundreds of Lenders Available",
                "Only Takes 2 Minutes to Check"
            ],
            "imageUrl": "https://cdn.myadoptimizer.com/maojsfiles/images/LogoAdvertiser_000131_b87736d1-48eb-43c5-a49d-0f76c1d97b58.png",
            "destUrl": "https://api.myadoptimizer.com/api/MAOHttpRedirect?src=https%3A%2F%2Finfo.floridacareercollege.com%2Fbusiness-office-administration%2F%3Fadkey%3DIS1CAEXN00%26ctc%3D877-425-6149%26utm_source%3Dcexplorer%26utm_medium%3Dcpc%26utm_campaign060118-fcc-cpc%26utm_content%3DFCC-Business%26CCK%3Dacbb214a-e69e-4394-bea0-3b48f6997cca%7Cfcc_business%26t%3DtestClickID&LandingPageID=43&EventID=acbb214a-e69e-4394-bea0-3b48f6997cca&AdNetworkAPIID=44&cpc=9.00&Brand=Florida Career College&Title=Earn A Business Office Administration Diploma - Start Building A Future You Can Be Proud Of&CB=1VawjEjip8ij5oaSZJZ0mw==&M=4XarSvqYDCayCqZpzLZFSg==&Weight=9.50&BidModifiers=50.00&NetworkAdID=458&SourceID=&LandingPageURL=",
            "impressionUrl": "https://api.myadoptimizer.com/api/MAOSaveResults?LandingPageID=43&AdNetworkAPIID=44&EventID=acbb214a-e69e-4394-bea0-3b48f6997cca&AdCampaignID=458&RequestTypeID=4",
            "displayUrl": "http://www.floridacareercollege.com/business-office-administration",
            "revenue": 9.00,
            "baseRevenue" : 6.00,
            "bidModifierLog": [
              "Consumer Credit: Good - Value: 50.00%",
              "States: CA - Value: -10.00%",
              "Tuesday: 14:18 - Value: 10.00%"
            ],
            "weight": 9.50,
            "statusId": 1,
            "trackingURL": "https://api.myadoptizer.com/api/MAOLeadTracking?AdNetworkAPIID=27&LandingPageID=24&EventID=8b448cc4-da0b-4f70-b180-c0c883282a49&IP=128.1.1.1&AdCampaignID=168"
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