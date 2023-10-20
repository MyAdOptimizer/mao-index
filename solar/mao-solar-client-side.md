<p align="center">
  <a href="https://myadoptimizer.com/">
    <img src="https://myadoptimizer.com/img/logo-blk.svg" alt="Logo" height="80">
  </a>
  <h3 align="center">MyAdOptimizer.com Client Side Integration Doc | Solar</h3>
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
    * [Specific Query String Parameters for Solar](#specific-query-string-parameters-for-solar)
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

* **ExtClickID:** Optional, tracking variable
> [!NOTE]
> This tracking variables requires special integration. You need to append it to the destURL property from the results returned by API call.

* CustomVar1: `Optional, tracking variable (Max length - 75)`
* CustomVar2: `Optional, tracking variable (Max length - 75)`
* CustomVar3: `Optional, tracking variable (Max length - 75)`
* CustomVar4: `Optional, tracking variable (Max length - 75)`
* CustomVar5: `Optional, tracking variable (Max length - 75)`


<h3>Specific Query String Parameters for <strong>Solar</strong></h3>

| Params Names               | Data Type | Allowed Values |
| :------------------------- | :-------: | :------------- |
| ZipCode*                   | string    | 5 char US zip code              |
| State*                     | string    | 2 char US state code (Uppercase) |
| MonthlyPowerBill*          | string    | $0 - $99, $100 - $149, $150 - $199, $200 - $249, $250 - $349, $350 - $399, $400 - $449, $450 - $499, $500 - $1000+ |
| UtilityProvider*           | string    | (See full list)[^1] Do NOT use commas inside Provider Names, as they're used as separators |
| RoofSunExposure*           | string    | Full Sun, Partially Shaded, Mostly Shaded, Not Sure |
| HomeOwner*                 | string    | Yes, No |
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

[^1]: **Utility Providers Full List**
4 Change,Acacia,AECO (Alabama Electric Company),Aiken Electric Cooperative,Alabama Power,Alameda Municipal Power,Alaska Electric Light & Power,Alaska Power and Telephone,
Alaska Villages Electric Cooperative,Allegheny Power,Alliant Energy,Alpena Power,Amana Society Service Co,Ambit,Ameren,American Electric Power,American Light and Power,Amigo Energy,
Anaheim Public Utilities,AP G&E,Apna,Appalachian Power,Arizona Public Service,Ashland Electric,Atlantic City Electric,Austin Energy,Avista Corp,Avista Utilities,Azusa Light & Water,
Baltimore Gas & Electric,Bangor Hydro Electric,Banning Electric Department,Basin Electric Power Cooperative,Batavia Municipal Electric,Bear Valley Electric,Belmont Municipial Light Department,
Benton PUD,Berkeley Electric Cooperative,Berkshire Company,Bethel Utilities,Big Rivers Electric Corporation,Biggs Electrical Department,Black Diamond Power,Black Hills Energy,Black Hills Power,
Black River Electric Cooperative,Block Island Power,Bounce Energy,Breeze,Brilliant,Burbank Water & Power,Burlington Electric Department,Calpine,Canby Electric,Cape Light Power,CenterPoint Energy,
Central Electric Power Cooperative Inc.,Central Hudson Gas & Electric,Central Maine Power,Central Montana Electric Power Cooperative,Central Power Electric Cooperative,Central Vermont Public Service,
CH Energy Group,Champion Energy Services,Chelan County Public Utility District,Cheyenne Light Fuel & Power,Choptank Electric Cooperative,Chugach Electric Association,Cirro,Citizens Choice Energy Jamestown BPU,
Citizens Electric of Lewisburg,Citizens Utilities Board,City & County of San Francisco,City of Banning,City of Dover,City of Hagerstown,City of Lewes,City of Mesa Utilities,City of Milford Electric Department,
City of Newark,City of Palo Alto Utilities,City of Redding Electric Utility,City of Santa Clara Power,City of Seaford,City of Tallahassee Utilities,City of Taunton,City Utilities of Springfield,
Clear View,Clearwater Power,CLECO,Cleco Power LLC,Cleveland Electric Illuminating Company,Colorado Springs Utilities,Colton Public Utilities and Public Service Department,
Colton Public Utilities Glendale Public Service Department,Columbia River Public Utility District,ComEd Electric Company,Company,Concord Municipal Light Plant,Connecticut Light & Power,
Connecticut Natural Gas,Consolidated Edison Company of New York (Con Edison),Consolidated Electric Cooperative,Consumers Energy,Copper Valley Electric Association,Coserv Electric,
CPS Energy,Dahlberg Light & Power,Dairyland Power Co-op,Danville Utilities,Dayton Power & Light,Delaware Electric Cooperative,Delmarva Power,Denton Municipal Eletric,Direct Energy,
Dominion Virginia Power,Douglas County Public Utility District,dPi Energy,DTE Energy (Detroit Edison),Duke Energy,Duke Energy Indiana,Duke Energy Kentucky,Duke Energy NC,Duke Energy Ohio,
Duke Energy SC,Duquesne Light,Eagle,Eagle Energy,East River Electric Cooperative,East River Electric Power Co-op,Easton Utilties,El Cerrito Electric,El Paso Electric Company,El Paso Electric Company,
Electric Database Publishing,Electric Power Board,Electrical District #2,Electrical District #3,ElectriCities,Emerald PUD,Empire District Electric,Empire District Electric Company,
Entergy,Entrust Energy,Eugene Water & Electric Board,Eversource Energy,Everything,Excel Energy,Farmington Electric Utility System,First Choice,First Texas Energy Corporation,FirstEnergy,
Fishers Island Utility Co Inc,Fitchburg Gas & Elec Light,Flint Energies,Florida Municipal Power Agency,Florida Power & Light,Florida Public Utility Company Palm Beach,Frontier,G & K Inc,
Gainesville Regional Utilities,Garland Power and Light,Georgetown Utility Services (GUS),Georgia Power,Gexa Energy,Glendale Water and Power,Glenwood Springs,Golden Valley Electric Association,
Grand Valley Power,Granite State Electric,Grant County Public Utility District,Great River Energy,Green Island Power Authority,Green Mountain Energy,Green Mountain Power,Gridley Municipal Utilities,
Groton Utilities,Gulf Power,GVEC,Hawaii Electric Light Company,Hawaiian Electric Company (HECO),Hawaiian Electric Industries,Healdsburg Municipal Electric Department,Henderson Municipal Power and Light,
High Plains Power,High West Energy,Hino,Hohokam Irrigation & Drainage District,Holden Municipal Light Department,Holland Board of Public Works,Holy Cross Energy Company,Hughes Power & Light,
Hutchinson Utilities Commission,IDACORP,Idaho Power,IGS Energy,Imperial Irrigation District,Independence Power and Light,Indiana Michigan Power,Indianapolis Power & Light,infintite,
Intermountain Power Agency,Intermountain Rural Electric Association,Interstate Power and Light Company,Island Energy,ITC Midwest,Jackson,JEA,Jersey Central Power and Light Company,Just Energy,
Kansas City Board of Public Utilities,Kansas City Power & Light,Kansas Gas & Electric,Kauai Island Utility Cooperative (KIUC),Kentucky Power,Kentucky Utilities,Kingsport Power (Appalachian Power),
Kissimmee Utility Authority,Klickitat Public Utility District,Knoxville Utilities Board,Kodiak Electric Association,Kona,Kuiggluum Kallugvia,L&O Power Co-op,Lake Worth Utilities,Lakeland Electric,
Lansing Board of Water & Light,LCEC,Lenoir City Utilities Board,Limunant,Lockhart Power,Lodi Electric Utility,Los Angeles Department of Water and Power,Louisville Gas & Electric,Lower Colorado River Authority,
Lower Valley Energy,Luminant,Madion Electric Department,Madison Gas and Electric,Magic Valley,Magnolia Electric,Maine Public Service,Marin Energy Authority,Marshall Municipal Utilities,
Mason County Public Utility District 3,Massachusetts Electric,Massachusetts Municipal Wholesale Electric Company (MMWEC),Maui Electric Company,MDU,Memphis Light Gas and Water,Merced Irrigation Disctrict,
Met-Ed,Mid Carolina Electric Cooperative,MidAmerican Energy,Minnesota Power,Minnkota Power Cooperative,Mission Power,Mississippi Power Company,Missouri River Energy Services,Modesto Irrigation District,
Mojave Electric Co-op,Monongahela Power,Montana Electric Cooperatives' Association,Montana-Dakota Utilities,Moreno Valley Electric Utility,Mountain Utilities,MP2 Energy,Mt Carmel Public Utility Co,
Municipal Light & Power,Nantucket Electric,Napakiak Ircinraq Power,Narragansett Electric,Nashville Electric Service,National Grid,Nebraska Public Power District,Nevada Power,New Leaf,
New York Power Authority (NYPA),New York State Electric & Gas (NYSEG),New-Mac Electric,Niagara Mohawk Power,North Carolina Electric Membership Corp.,North Central Power,North Little Rock Electric,
Northeast Utilities,Northern Indiana Public Service Company,Northern States Power,Northwestern Energy,Northwestern Wisconsin Elec Company,NOVEC,NRG Energy,NSTAR,NV Energy,Ocala Electric,
Ohio Edison,Ohio Power,Oklahoma Gas & Electric,Omaha Public Power District,Omya Inc,Oncor Electric (Formerly TXU),Orange & Rockland,Orange & Rockland (O&R),Orlando Utilities Commission,
Other,Otter Tail Power Company,Our energy,Owensboro Municipal Utilities,Pacific Gas & Electric,PacifiCorp,PacifiCorp (Pacific Power),PacifiCorp (Rocky Mountain Power),Palo Alto Electric Utility,
Pasadena Water & Power,Peabody Municipal Light Plant,PECO,Penelec,Penn Power,Penny wise,People,PEPCO,Pike County Light & Power Company,PNM,Portland General Electric,PowerSouth Energy Cooperative Inc.,
PPL,Progress Energy Carolinas,Progress Energy Florida,PSEG Long Island formerly LIPA,Public Service Co of Colorado,Public Service Company of New Mexico,Public Service Company of Oklahoma,
Public Service Electric and Gas Company PSE&G,Public Service of NH,Puget Sound Energy,Rappahannock Electric Cooperative,Reach,Reading Municpial Light Department,Reliant Energy,
Riverside Public Utilities,Rochester Gas & Electric,Rochester Public Utilities,Rockland Electric,Rocky Mountain Power,Roseville Electric,Rural Valley Electric Co.,Rushmore Electric Cooperative,
Sacramento Municipal Utility District,Salem Electric,Salt River Electric,Salt River Project,San Diego Gas & Electric,Santee Cooper,Seattle City Light,Sharyland Utilities LP,Sierra Pacific Power,
Sierra-Pacific Power,Silicon Valley Power,Snohomish County Public Utility District (PUD),Source,South Carolina Electric & Gas Company,South Central Power Company,Southern California Edison,
Southern California Public Power Authority,Southern Indiana Gas & Elec Company,Southern Maryland Electric Cooperative,Southwest Mississippi Electric Power Association,Southwest Power and Light,
Southwestern Electric Power Co,Southwestern Electric Power Company (SWEPCO),Southwestern Public Service Co,Spark Energy,Springfield City Water Light & Power,SRP/Salt River Project,Star Tex Power,
Star Trex,Stream Energy,Sulphur Springs Valley Electric Cooperative,Summer,Surprise Valley Power,Sussex Rural Electric Cooperative,SWEPCO,Tacoma Power,Tanana Power,Tara Energy,TECO,
Tennessee Jackson Energy Authority,Tennessee Valley Authority,Texas Electric Service Company,Texpo,Tillamook PUD,Toledo Edison,Town of Berlin,Town of Clayton,Town of Mansfield,Town of Middletown,
Town of Smyrna,Tri Eagle Energy,Trico Electric Cooperative,Tri-County Electric,Trinity PUD,Tru Smart,Truckee-Donner Public Utilities District,True Electric,Tucson Electric Power,
Turlock Irrigation District,TXU,UGI Utilities Inc.,Ukiah Municpial Utility District,Union Electric,Unisource,United Illuminating,United Power Inc,UNITIL,Unitil (Fitchburg Gas and Electric) ,
Unitil Corporation,Upper Missouri G&T Cooperative,Upper Peninsula Power Company,Valley Electric Association,Vernon Light & Power,Veteran,Vineland Municipal Electric Utility,
Virginia Electric & Power,Wallingford Electric,Wasco Electric,We Energies,Wellsboro Electric Company,West Oregon Electric Cooperative,Westar Energy,Western Massachusetts Electric,
Wheeling Electric Power (AEP Ohio),Wiregrass Electric Cooperative,Wisconsin Electric Power,Wisconsin Power and Light Company,Wisconsin Public Service Corporation,WMECO,
Wyandotte Municipal Services,Xcel Energy,YEP
