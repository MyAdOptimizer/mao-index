<p align="center">
  <a href="https://myadoptimizer.com/">
    <img src="https://myadoptimizer.com/img/logo-blk.svg" alt="Logo" height="80">
  </a>
  <h3 align="center">MyAdOptimizer.com Client Side Integration Doc | Life Insurance</h3>
  <p align="center">
    Learn how to integrate the <strong>MAO Client Side</strong> by following these steps
    <br />
    <a href="https://myadoptimizer.com">View Site</a>
    ·
    <a href="https://myadoptimizer.com/contact">Report Bug</a>
  </p>
</p>

## Table of Contents

* [Client Side](#client-side)
    * [Setup](#setup)
    * [Specific Query String Parameters for Life Insurance](#specific-query-string-parameters-for-life-insurance)
        - [LocalStorage integration](#LocalStorage-Integration)
* [External Ad Networks Setup (OPTIONAL)](#external-ad-networks-setup-optional)

## Client Side

## Setup

MyAdOptimizer.com will provide a Javascript snippet back to you to add to your new `Thank You` page as follows:
```html
<script src="https://cdn.myadoptimizer.com/maojsfiles/landingpagesjs/{{LandingPageToken}}.js"></script>
```

* {{LandingPageToken}}: `Token that will be provided by your account manager`
* Div Element: `Aggregated results will be rendered automatically once the thank you page loads on the user browser. An HTML DIV element with ID="target" must be created in the Thank-You page as results will be rendered inside that element.`
* Default CSS Theme: `MyAdOptimizer provides a default CSS; however, if you wish to change it and create your own to match your landing page theme, please contact your account manager`
* Device Type (Desktop or Mobile): `This is automatically inferred when using Client Side (JavaScript) integration`

To ensure that each ad network gets the parameter values they require we ask that you setup a new `Thank You` page and pass the below parameters in the query string.
The aggregated results will be rendered once they `Thank You` page loads on the user’s browser.
```diff
- All values should be passed in your TY page query string
- If a value is not currently passed please let us know
```

Generic Query String Parameters

* SourceID: `Optional, tracking variable`

* **ExtClickID:** Optional, tracking variable
> [!NOTE]
> This tracking variables requires special integration. You need to append it to the destURL property from the results returned by API call.

* CustomVar1: `Optional, tracking variable (Max length - 75)`
* CustomVar2: `Optional, tracking variable (Max length - 75)`
* CustomVar3: `Optional, tracking variable (Max length - 75)`
* CustomVar4: `Optional, tracking variable (Max length - 75)`
* CustomVar5: `Optional, tracking variable (Max length - 75)`

<h3>Specific Query String Parameters for <strong>Life Insurance</strong></h3>


| Params Names | Data Type | Allowed Values |
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
| TabaccoUse*         | string | Yes, No |
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

## LocalStorage Integration

In order to use LocalStorage instead Querystring, set up the parameters names & values stated above by adding them using a MAO JS function called **setMAOLocalStorageValue**. This method expects a key/value pair.

The function setMAOLocalStorageValue need two paramets

- Property name & Property value

For example:

```Javascript
/*
@param{string} sParam - Property Name
@param{*} sValue - Property Value
*/
setMAOLocalStorageValue('State', CA);
setMAOLocalStorageValue('ZipCode', 90291);
// Output: Added value succesfully
```

Once you have set up all parameters values, you need to invoke the function **initMAO** to render all campaigns.

**initMAO** function need two parameters

- Target HTML ID & Render mode
  For Example:

```HTML
//HTML Structure
<div id="target"> Rendered campaings ... </div>
```

```Javascript
/*
@param{string} TargetHtmlControlID
@param{number} GlobalRenderMode (1- Live , 2- Test)
*/
InitMAO('target', 1);
```

## Click to call (RenderMode 3) 

### Callback properties

* **CampaignPhoneNumber:** `New!` A unique phone number assigned to the campaign to track and measure calls.

* **CallToAction:** `New!` Text displayed on a clickable button or element, encouraging users to initiate a phone call.

* **AdResultCallStatusID:** `New!` An ID representing the campaign's call status, where:

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

### Example Callback

```JSON
{
    "advertiserId": "100",
    "AdvertiserName": "Advertiser Name 01 - 100",
    "AdNetworkAPIID": 76,
    "Title": "Fixed Mortgage Rates from 5.7 rate 6.1 Apr",
    "AdCopyVersion": 1,
    "Description": "FHA, VA, 30 Year Fixed, 15 Year Fixed <br /> Cash Out and Home Equity Options <br /> View Rates & Payments <br /> Calculate Home Equity Payments",
    "CPC": 15.75,
    "BaseCPC": 15,
    "Logo": "https://cdn.myadoptimizer.com/maojsfiles/images/LogoAdvertiser_000000_00000000-0000-0000-0000-000000000000.jpg",
    "BrandName": "Advertiser Name 01",
    "NetworkSort": 1,
    "NetworkAdID": "1284",
    "DisplayUrl": "Advertiser Name 01.com/MortgageRates",
    "PayLoad": "",
    "Weight": 15.75,
    "CB": "XXXXXXXXXXXXXXXXXXXXXXX",
    "M": "XXXXXXXXXXXXXXXXXXXXXXX",
    "BidModifierPercentange": 5,
    "BidFloor": 0,
    "RequestDuration": 539,
    "AdResultLogStatusId": 1,
    "AdNetworkName": "MAO Open Exchange",
    "SourceID": "",
    "ExtClickId": "",
    "ExtSearchID": "",
    "LandingPageURL": "ThankYouDemo.html",
    "bidModDescription": [
        "Consumer Credit: Excellent - Value: 5%"
    ],
    "CustomVar1": "",
    "CustomVar2": "",
    "CustomVar3": "",
    "CustomVar4": "",
    "CustomVar5": "",
    "DailyFilledRate": 0,
    "CampaignDailyCap": 1500,
    "CampaignPhoneNumber": "+11234567890",
    "CallToAction": "Call Now",
    "AdResultCallStatusID": 1,
    "DestinationURL": "https://maofunctionstest.azurewebsites.net/api/MAOHttpRedirect?src=https%3A%2F%2Fwww.Advertiser Name 01.com%2Fmortgagerates%3Futm_source%3Ddirectbidder1284&LandingPageID=10&EventID=XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX&AdNetworkAPIID=76&cpc=15.75&Brand=Advertiser Name 01&Title=Fixed Mortgage Rates from 5.7 rate 6.1 Apr&CB=XXXXXXXXXXXXXXXXXXXXXXX&M=XXXXXXXXXXXXXXXXXXXXXXX&Weight=15.75&BidModifiers=5&NetworkAdID=1284&SourceID=&LandingPageURL=ThankYouDemo.html&AdId=100&AdCopyVersion=1&CustomVar1=&CustomVar2=&CustomVar3=&CustomVar4=&CustomVar5=",
    "findIndex": 0
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
