<p align="center">
  <a href="https://myadoptimizer.com/">
    <img src="https://myadoptimizer.com/img/logo-blk.svg" alt="Logo" height="80">
  </a>
  <h3 align="center">MyAdOptimizer.com Server API Integration Doc | Home Services</h3>
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
    * [Specific Query String Parameters for Personal Loans](#specific-query-string-parameters-for-personal-loans)
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


<h3>Specific Query String Parameters for <strong>Home Services</strong></h3>

| Query String Params Names | Data Type | Allowed Values |
| :------------------------ | :-------: | :------------- |
| ZipCode*                   | string    | 5 char US zip code              |
| State*                     | string    | 2 char US state code (Uppercase) |
| ProjectServiceType*        | string    | Roofing, Gutters, Windows/Doors, Kitchen/Bathroom, Home Security, Pest Control, Lawn Care, Solar Roofing Type, Solar Power Bill |
| ProjectTypesConcentration* | string    | <table> <tr> <td>Roofing</td> <td>Asphalt Only, Tile Only, Metal Only, Foam Only, Tar & Gravel Only, Wood Shingles Only, Slate Only</td> </tr> <tr> <td>Gutters</td> <td>Residential, Commercial</td> </tr> <tr><td>Windows/Doors</td><td>1 to 10 Windows, 1 to 10 Doors</td></tr> <tr><td>Kitchen/Bathroom</td><td>Bathroom Remodel, Walk-In Shower Only, Walk-In Tub Only, Bathtub to Shower Only, Kitchen Remodel</td></tr> <tr><td>Home Security</td><td>Security Intrusion, Fire Detection</td></tr> <tr><td>Pest Control</td><td>Bugs/Insects, Rodents, Birds/Bats, Small Animals, Termites, Ants, Bees/Wasps, Fleas, Spiders</td></tr> <tr><td>Lawn Care</td><td>Landscaping, Lawn Care, Gardening, Sod Installation, Tree Planting, Artificial Turf Installation</td></tr> <tr><td>Solar Roofing Type</td><td>Full Sun, Partially Shaded, Mostly Shaded, Not Sure</td></tr> <tr><td>Solar Power Bill</td><td>$0 - $99, $100 - $149, $150 - $199, $200 - $249, $250 - $349, $350 - $399, $400 - $449, $450 - $499, $500 - $1000+</td></tr> </table> |
| ProjectScope*              | string    | Replace New, Repair Existing, Other |
| ProjectTimeline*           | string    | Immediate, Within 2 weeks, Within 1 month, Unsure |
| HomeOwner*                 | string    | Yes, No |
| Gender*                    | string    | Male, Female, Other |
| Married*                   | string    | Yes, No |
| MilitaryStatus*            | string    | Yes, No |
| Age                        | integer   | 1 - 99 |
| FName ±                    | string    |  |
| LName ±                    | string    |  |
| Email ±                    | string    |  |
| Phone ±                    | string    |  |
| Address ±                  | string    |  |
| City ±                     | string    |  |
| MediaChannel               | string    | Social, Facebook, Native, Email, Display, SEM, SEO, SMS, Push, Affiliate, ChannelA, ChannelB, ChannelC, ChannelD, ChannelE |

*Case Sensitive

±PII Fields - These values are not constraints and will not be evaluated by MAO

### API Response

* **destURL:** This is the Click URL. Please use the value from this field when a click is triggered.

* **impressionUrl:** This is a call back URL so that MAO can track live impressions. If a listing is displayed in your result set, please trigger the impressionUrl of  that listing.

* **displayUrl:** This is the value from “Display URL” in the Campaign Ad Copy.

* **trackingURL:** This is a Image Pixel to track leads or form submits from Clicks. This is optional to implement, but it is used to provide traceability from a click to a lead submit.

* **revenue:** Actual payout per click based on bid modifiers.

* **baseRevenue:** Base bid per click. It'll vary based on bid modifiers.

* **bidModifierLog:** The log that shows  how the baseRevenue bid was modified.

* **advertiserName:** The name of the advertiser - The ID of the advertiser.

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
    "searchResultId": "3e9c9fa9-bfb7-47bd-8221-d2d111ebde38",
    "duration": 595,
    "items": [
        {
            "itemId": "159",
            "brandName": "personalloans",
            "networkSort": 1,
            "requestDuration": 374,
            "sourceID": null,
            "extClickID": null,
            "advertiserId": "53",
            "advertiserName": "RateZip - 1066",
            "displayName": "Save time. Save paperwork. Save Dollars.",
            "headline": "Personal loans made simple. And so affordable.",
            "blurbs": [
                "Personal loans can be so simple. And so affordable.",
                "We're making loans surprisingly painless",
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
