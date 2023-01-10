<p align="center">
  <a href="https://myadoptimizer.com/">
    <img src="https://myadoptimizer.com/img/logo-blk.svg" alt="Logo" height="80">
  </a>
  <h3 align="center">MyAdOptimizer.com Client Side Integration Doc | Auto Insurance</h3>
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
    * [Specific Query String Parameters for Auto Insurance](#specific-query-string-parameters-for-auto-insurance)
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

To ensure that each ad network gets the parameter values they require we ask that you setup a new `Thank You` page and pass the below parameters in the query string.
The aggregated results will be rendered once they `Thank You` page loads on the user’s browser.
```diff
- All values should be passed in your TY page query string
- If a value is not currently passed please let us know
```

Generic Query String Parameters

* SourceID: `Optional, tracking variable`
* ExtClickID: `Optional, tracking variable`
* CustomVar1: `Optional, tracking variable (Max length - 75)`
* CustomVar2: `Optional, tracking variable (Max length - 75)`
* CustomVar3: `Optional, tracking variable (Max length - 75)`
* CustomVar4: `Optional, tracking variable (Max length - 75)`
* CustomVar5: `Optional, tracking variable (Max length - 75)`


<h3>Specific Query String Parameters for <strong>Auto Insurance</strong></h3>

| Params Names | Data Type | Allowed Values |
| :------------------------ | :-------: | :------------- |
| ZipCode*                   | string    |  5 char US zip code             |
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
| Married*                  | string    | Yes, No |
| MilitaryStatus*            | string    | Yes, No |
| SR22*                      | string    | Yes, No |
| VehicleMake*               | string    | Acura, Audi, BMW, Buick, Cadillac, Chevrolet, Chrysler ,Dodge, Ford ,GMC, Honda, Hyundai, Infiniti, Isuzu, Jaguar, Jeep, Kia, Lexus, Mazda, Mercedes, Mercury, Nissan, Porsche, Subaru, Toyota, Volvo, Other |
| VehicleYear               | integer   | 2021,2020,2019,2018,2017,2016,2015,2014,2013,2012,2011,2010,2009,2008,2007, 2006,2005,2004,2003,2002,2001,2000,1999,1998,1997,1996,1995,1994,1993,1992, 1991, 1990 |
| VehiclesToInsure          | integer   | 1,2,3 |
| Age                        | integer  | 1 - 99 |
| FName ±                    | string    |  |
| LName ±                   | string    |  |
| Email ±                    | string    |  |
| Phone ±                    | string    |  |
| Address ±                  | string    |  |
| City ±                     | string    |  |
| MediaChannel                | string    | Social, Facebook, Native, Email, Display, SEM, SEO, SMS, Push, Affiliate, ChannelA, ChannelB, ChannelC, ChannelD, ChannelE |

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
