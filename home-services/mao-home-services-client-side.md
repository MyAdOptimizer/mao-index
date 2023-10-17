<p align="center">
  <a href="https://myadoptimizer.com/">
    <img src="https://myadoptimizer.com/img/logo-blk.svg" alt="Logo" height="80">
  </a>
  <h3 align="center">MyAdOptimizer.com Client Side Integration Doc | Home Services</h3>
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
    * [Specific Query String Parameters for Personal Loans](#specific-query-string-parameters-for-home-services)
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


<h3>Specific Query String Parameters for <strong>Home Services</strong></h3>

| Params Names               | Data Type | Allowed Values |
| :------------------------- | :-------: | :------------- |
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