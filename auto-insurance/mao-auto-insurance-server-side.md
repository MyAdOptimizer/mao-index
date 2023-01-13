<p align="center">
  <a href="https://myadoptimizer.com/">
    <img src="https://myadoptimizer.com/img/logo-blk.svg" alt="Logo" height="80">
  </a>
  <h3 align="center">MyAdOptimizer.com Server API Integration Doc | Auto Insurance</h3>
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
    * [Specific Query String Parameters for Auto Insurance](#specific-query-string-parameters-for-auto-insurance)
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
* CustomVar1: `Optional, tracking variable (Max length - 75)`
* CustomVar2: `Optional, tracking variable (Max length - 75)`
* CustomVar3: `Optional, tracking variable (Max length - 75)`
* CustomVar4: `Optional, tracking variable (Max length - 75)`
* CustomVar5: `Optional, tracking variable (Max length - 75)`


<h3>Specific Query String Parameters for <strong>Auto Insurance</strong></h3>

| Query String Params Names | Data Type | Allowed Values |
| :------------------------ | :-------: | :------------- |
| ZipCode*                   | string    | 5 char US zip code              |
| State*                     | string    | 2 char US state code (Uppercase) |
| Accidents*                 | string    | None,1,2,3+ |
| BusinessOwner*             | string    | Yes, No |
| CreditScore*               | string    | Excellent, Good, Fair, Poor |
| CurrentInsurer*            | string    | Allstate, GEICO, Farmers, Liberty Mutual, Progressive, Nationwide, State Farm, Travelers, USAA, Other |
| Drivers*                   | string    | 1,2,3+ |
| DUI*                       | string    | Yes, No |
| Gender*                    | string    | Male, Female, Other |
| HomeOwner*                 | string    | Yes, No |
| InsuredStatus*             | string    | Yes, No |
| Married*                   | string    | Yes, No |
| MilitaryStatus*            | string    | Yes, No |
| SR22*                      | string    | Yes, No |
| VehicleMake*               | string    | Acura, Audi, BMW, Buick, Cadillac, Chevrolet, Chrysler ,Dodge, Ford ,GMC, Honda, Hyundai, Infiniti, Isuzu, Jaguar, Jeep, Kia, Lexus, Mazda, Mercedes, Mercury, Nissan, Porsche, Subaru, Toyota, Volvo, Other |
| VehicleYear               | integer   | 2021,2020,2019,2018,2017,2016,2015,2014,2013,2012,2011,2010,2009,2008,2007, 2006,2005,2004,2003,2002,2001,2000,1999,1998,1997,1996,1995,1994,1993,1992, 1991, 1990 |
| VehiclesToInsure          | integer   | 1,2,3 |
| Age                       | integer   | 1 - 99 |
| FName ±                    | string    |  |
| LName ±                   | string    |  |
| Email ±                    | string    |  |
| Phone ±                    | string    |  |
| Address ±                  | string    |  |
| City ±                     | string    |  |
| MediaChannel                | string    | Social, Facebook, Native, Email, Display, SEM, SEO, SMS, Push, Affiliate, ChannelA, ChannelB, ChannelC, ChannelD, ChannelE |

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
* advertiserName: `The name of the advertiser - The ID of the advertiser`

Example response: 
 ```javascript
{
    "searchResultId": "3e9c9fa9-bfb7-47bd-8221-d2d111ebde38",
    "duration": 595,
    "items": [
        {
            "itemId": "159",
            "brandName": "esurance",
            "networkSort": 1,
            "requestDuration": 374,
            "sourceID": null,
            "extClickID": null,
            "advertiserId": "53",
            "advertiserName": "Assurance IQ - 249",
            "displayName": "Save time. Save paperwork. Save Dollars.",
            "headline": "Car insurance can be so simple. And so affordable.&lt;br /&gt;We&#39;re making insurance surprisingly painless&lt;br /&gt;Click for quote today and save big!&lt;br /&gt;",
            "blurbs": [
                "Car insurance can be so simple. And so affordable.",
                "We're making insurance surprisingly painless",
                "Click for quote today and save big!"
            ],
            "imageUrl": "https://cdn.myadoptimizer.com/maojsfiles/images/LogoAdvertiser_000000_20f8cac8-121a-4d17-9a26-24d744b8b75b.JPG",
            "displayURL": "http://www.google.com"
            "destUrl": "https://api.myadoptimizer.com/api/MAOHttpRedirect?src=https://www.esurance.com/&LandingPageID=16&EventID=3e9c9fa9-bfb7-47bd-8221-d2d111ebde38&AdNetworkAPIID=16&cpc=11.27&Brand=esurance&Title=Save time. Save paperwork. Save Dollars.&CB=2mh319GLuFmMowM78sQmQw==&M=RatzBRmIdXToBqVWXvRlmw==&Weight=11.27&BidModifiers=50.00&NetworkAdID=159&SourceID=&LandingPageURL=",
            "impressionUrl": "https://api.myadoptimizer.com/api/MAOSaveResults?LandingPageID=26&AdNetworkAPIID=29&EventID=ae9540ce-7f31-405e-b21c-f11e7a2168b8&AdCampaignID=311&RequestTypeID=4",
            "revenue": 11.27,
            "baseRevenue" : 7.51,
            "bidModifierLog": [
              "Consumer Credit: Good - Value: 50.00%",
              "States: CA - Value: -10.00%",
              "Tuesday: 14:18 - Value: 10.00%"
            ],
            "weight": 11.27,
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
