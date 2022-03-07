<p align="center">
  <a href="https://myadoptimizer.com/">
    <img src="https://myadoptimizer.com/img/logo-blk.svg" alt="Logo" height="80">
  </a>
  <h3 align="center">MyAdOptimizer.com Client Side Integration Doc | Mortgage Refinance</h3>
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
    * [Specific Query String Parameters for Mortgage Refinance](#specific-query-string-parameters-for-mortgage-refinance)
        - [LocalStorage integration](#LocalStorage-Integration)
* [External Ad Networks Setup (OPTIONAL)](#external-ad-networks-setup-optional)

## Client Side

## Setup



MyAdOptimizer.com will provide a Javascript snippet back to you to add to your new `Thank You` page as follows:
```html
<script src="https://cdn.myadoptimizer.com/maojsfiles/landingpagesjs/{{YOUR_MYADOPTIMIZER_ID}}.js"></script>
```
* {{YOUR_MYADOPTIMIZER_ID}}: `Token that will be provided by your account manager`
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

<h3>Specific Query String Parameters for <strong>Mortgage Refinance</strong></h3>

| Params Names | Data Type | Allowed Values |
| :------------------------ | :-------: | :------------- |
| zipcode         | string  |       5 char US zip code         |  
| State*           | string  | 2 char US state code (Uppercase)  |
| creditscore*     | string  | Excellent, Good, Fair, Poor |
| loanbalance     | int  |      0-10000000                       |
| propertyvalue   | int  |           0-10000000                  |
| CashOut*    | string |  Yes, No       |
| MediaChannel*                | string    | Social, Facebook, Native, Email, Display, SEM, SEO, SMS, Push, Affiliate, ChannelA, ChannelB, ChannelC, ChannelD, ChannelE |
| MilitaryStatus* | string  | Yes, No |
| EmploymentStatus*    | string |  Employed, Self-Employed, Retired, Not Employed       |
| PropertyUse*     | string  | Primary Home, Second Home, Rental Property |
| PropertyType*     | string  | Single Family, Multi-Unit, Condo/Townhome, Mobile, Other   |
| FName ±                    | string    |  |
| LName ±                    | string    |  |
| Email ±                    | string    |  |
| Phone ±                    | string    |  |
| Address ±                  | string    |  |
| City ±                     | string    |  |

*Case Sensitive

±PII Fields

<h3>Additional Optional Parameters for <strong>Transparent.ly</strong></h3>

| Param Name                | Data Type | Allowed Values |
| :------------------------ | :-------: | :------------- |
| currentinterestrate         | decimal | 0 - 99.99 |
| timeframetobuy              | string  | 30 days (Offer Pending or Signed Purchase Agreement), 2-3 Months, 3-6 Months, Researching Options |
| currentmortgageprovider     | string  | AAG/American Advisors Group, AmeriHome Mortgage, AmeriSave Mortgage, Bank of America, Bank of England, Truist Financial, Better Mortgage, Caliber Home Loans, Carrington Mortgage, Cenlar, Chase, Citi, Citizens Bank, CrossCountry Mortgage, Ditech, Fairway Independent Mortgage, Fifth Third Bank, Finance of America Mortgage, First Guaranty Mortgage Corp, Freedom Mortgage Corp, Guaranteed Rate, Homepoint Financial, Huntington National Bank, LoanCare, loanDepot, Merrill Lynch, Morgan Stanley, Mr. Cooper/Nationstar, Navy Federal Credit Union, New American Funding, New Day USA, NewRez, Ocwen, PenFed Credit Union, PennyMac Loan Services, PHH Mortgage, PNC Mortgage, Quicken Loans Inc, Rocket Mortgage, RoundPoint Mortgage, Shellpoint, Specialized Loan Servicing, Sun West Mortgage, SunTrust, United Share Financial Services, United Wholesale Mortgage, US Bank Home Mortgage, USAA Federal Savings Bank, Veterans United, Wells Fargo & Company, Other, I Don't Know, No Lender (Loan Paid Off) |

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
