<p align="center">
  <a href="https://myadoptimizer.com/">
    <img src="https://myadoptimizer.com/img/logo-blk.svg" alt="Logo" height="80">
  </a>
  <h3 align="center">MyAdOptimizer.com Client Side Integration Doc | Education</h3>
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
    * [Specific Query String Parameters for Education](#specific-query-string-parameters-for-education)
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

<h3>Specific Query String Parameters for <strong>Education</strong></h3>

<table>
    <tr>
        <th> Prams Name</th>
        <th> Data type</th>
        <th colspan=2> Allowed Values</th>
    </tr>
    <tr>
        <td>ZipCode</td>
        <td>string</td>
        <td colspan=2></td>
    </tr>
    <tr>
        <td>State*</td>
        <td>string</td>
        <td colspan=2 >2 char US code (Uppercase)</td>
    </tr>
    <tr>
        <td>AdPlacement*</td>
        <td>string</td>
        <td colspan=2 >ICF, No Matches, After Matches, API, High School, Ad Unit, Organic Exit Pop, Paid Search Exit Pop Program Listings - Widget**, Program  Listings - Static**</td>
    </tr>
    <tr>
        <td>AreaOfStudy* </td>
        <td>String</td>
        <td colspan=2>
            Arts / Design / Fashion, Bootcamp, Business, Communication & Multimedia, Computers & IT, Cosmetology & Beauty, Criminal Justice & Law Enforcement, Culinary Arts & Hospitality, Education & Teaching, General Studies / Undecided, Health & Medical / Nursing, Legal
            Professions, Massage Therapy & Healing Arts, Political Science, Psychology & Social Work, Religious Studies,Trades & Careers, Counseling, ANY
        </td>
    </tr>
    <tr>
        <td rowspan=19> Concentration*</td>
        <td rowspan=19> string </td>
        <td> Arts / Design / Fashion </td>
        <td>Design & Visual Communications, Fashion/Apparel Design, Film and Theater, Graphic Design, Industrial Design, Interior Design, Photography, Visual Arts, ANY</td>
    </tr>
    <tr>
        <td>Bootcamp</td>
        <td>
            Data Analytics, Cyber Security, Coding, Software Engineering, General boot camp programs, Project Management, FinTech, Digital Marketing, UI-UX, Web Development, ANY
        </td>
    </tr>
    <tr>
        <td>Business</td>
        <td>
            Accounting & Related Services, Administrative & Secretarial Services, Business Communications, E-Commerce/Business, Economics, Entrepreneurship & Small Business, Fashion and Apparel, Finance, General Business, Green & Sustainable Management, Hospitality
            & Restaurants, Human Resources, Information Systems Management, International, Business, Management, Marketing, Property Management / Real Estate, Public & Non-Profit Administration, Public Relations, Retail & Sales, Supply Chain Management, Business Administration, Business Analytics, Business Intelligence, Organizational Leadership, Project Management, Taxation, ANY
        </td>
    </tr>
    <tr>
        <td>Communication & Multimedia</td>
        <td>
            Advertising, Animation & Video Graphics, Commercial & Advertising Art, Computer Media Applications, Design & Visual Communications, Film/Video & Cinematography, Graphic Design, Intermedia/Multimedia, Photography, Recording Arts Technology, Web
            Design, ANY
        </td>
    </tr>
    <tr>
        <td>Computers & IT</td>
        <td>
            Computer Science, Computer Support Services, Computer Systems Security, Networking, Software Development, Systems Administration, Telecommunications, Web Design and Internet, Analytics & Data Science, Engineering, Information & Library Sciences, Information Technology/Systems, Product Manager, ANY
        </td>
    </tr>
    <tr>
        <td>Cosmetology & Beauty</td>
        <td>
            Barbering/Barber, Cosmetology/Cosmetologist, Esthetician & Skin Care, Hair Styling & Hair Design, Make-Up Artist/Specialist, Manicurist/Nail Specialist, ANY
        </td>
    </tr>
    <tr>
        <td>Criminal Justice & Law Enforcement</td>
        <td>
            Correctional Officer (Prison Officer), Criminal Justice & Law Enforcement/Police, Fire Science, Forensics/Crime Scene Investigation, Homeland Security, Security Services,
            Criminal Justice, Criminology, ANY
        </td>
    </tr>
    <tr>
        <td>Culinary Arts & Hospitality</td>
        <td>Baking and Pastry Arts, Culinary Arts, Food Services, Hospitality Management, Restaurant & Food Services, Tourism & Travel Management, ANY</td>
    </tr>
    <tr>
        <td>Education & Teaching</td>
        <td>
            Administration & Leadership, Curriculum and Instruction, Early Childhood Education, Education and Teaching, General Education, Secondary Education, Educational Technology, Elementary Education, Music Education, Reading & Literacy, Special Education, Teaching, ANY
        </td>
    </tr>
    <tr>
        <td>General Studies / Undecided</td>
        <td>General Studies, History, Liberal Arts, Undecided, Writing, ANY</td>
    </tr>
    <tr>
        <td>Health & Medical / Nursing</td>
        <td>
            Alternative Medicine/Healing Arts, Bachelors of Nursing (BSN), Dental Assisting, Dental Hygienist, Diagnostic & Treatment Technician, General Nursing, Gerontology, Global Health, Health Information Technology/Records, Healthcare Administration, Human Services/Social Work, Medical Assistant, Medical Insurance Biller/Coder, Medical Office Assistant, Medical Transcriptionist, Nursing - DNP, Nursing - Licensed Practical/Vocational Nurse Training (Certificate), Nursing - MSN, Nursing - Registered Nurse (AAS), Nursing - RN to BSN, Nursing Assistant (CNA), Personal Training / Nutrition, Pharmacy Technician/Assistant, Phlebotomy / Clinical Medical Lab. Technician, Physical Therapy & Rehabilitation, Psychology, Surgical Technologist, Ultrasound Technician, Veterinary Medicine, X-Ray/Radiologic Technician, Emergency Management, Nurse Education, Nurse Practitioner (RN Required), Public Health, Speech Pathology/Therapy, Entry-Level Healthcare Programs, ANY
        </td>
    </tr>
    <tr>
        <td>Legal Professions</td>
        <td>Court Reporting, Juris Doctor, Legal Administrative Assistant, Legal Assistant/Paralegal, Legal Studies, ANY</td>
    </tr>
    <tr>
        <td>Massage Therapy & Healing Arts</td>
        <td>Healing Arts & Alternative Medicine, Massage Therapy, ANY</td>
    </tr>
    <tr>
        <td>Political Science</td>
        <td>Political Science, ANY</td>
    </tr>
    <tr>
        <td>Psychology & Social Work</td>
        <td>
            Business & Organizational Psychology, Clinical Psychology, Counseling Psychology, Forensic Psychology/Crime Scene Investigator, General Psychology, Human Services/Social Work, Sport Psychology, Behavioral Psychology, Child Psychology, Educational Psychology, ANY
        </td>
    </tr>
    <tr>
        <td>Religious Studies</td>
        <td>Christian Studies, Ministry, Religious Studies, Theology, ANY</td>
    </tr>
    <tr>
        <td>Trades & Careers</td>
        <td>Aircraft Maintenance, Auto Mechanic, Autobody Repair, Aviation, CAD Drafting and Design, Computer Installation & Repair, Computer Systems Technology, Construction Management, Electrician, Engineering Technology/Technicians, HVAC, Laboratory Technician, Plumbing Technology/Plumber, Telecommunications Technology, Truck Driving, Welding Technology/Welder, ANY</td>
    </tr>
    <tr>
        <td>Counseling</td>
        <td>Addictions & Recovery, Counseling, Family Counseling, Mental Health Counseling, School Counseling, ANY</td>
    </tr>
    <tr>
        <td>ANY</td>
        <td>ANY</td>
    </tr>
    <tr>
        <td>DegreeLevel*</td>
        <td>string</td>
        <td colspan=2>CERTIFICATE, ASSOCIATES, BACHELORS, MASTERS, DOCTORATE</td>
    </tr>
    <tr>
        <td>HighSchoolGradYear</td>
        <td>string</td>
        <td colspan=2>2023+, 2023, 2022, 2021, 2020, 2019, 2018, 2017, 2016, 2015, 2014, 2013, 2012, 2011, 2010, 2009, 2008, 2007, 2006, 2005, 2004, 2003, 2002, 2001, 1990</td>
    </tr>
    <tr>
        <td>HighestEducationLevel*</td>
        <td>string</td>
        <td colspan=2 >STILL_IN_HIGH_SCHOOL, NO_HIGH_SCHOOL_OR_GED, HIGH_SCHOOL, SOME_COLLEGE, ASSOCIATES_DEGREE, BACHELORS_DEGREE, MASTERS_DEGREE, DOCTORAL_DEGREE, GED</td>
    </tr>
    <tr>
        <td>LearningPreference*</td>
        <td>string</td>
        <td colspan=2>CAMPUS, ONLINE, HYBRID, ANY</td>
    </tr>
    <tr>
        <td>LikelihoodToEnroll*</td>
        <td>string</td>
        <td colspan=2>NOT_LIKELY, SOMEWHAT_LIKELY, VERY_LIKELY</td>
    </tr>
    <tr>
        <td>MediaChannel*</td>
        <td>string</td>
        <td colspan=2>Social, Facebook, Native, Email, Display, SEM, SEO, SMS, Push, Affiliate, ChannelA, ChannelB, ChannelC, ChannelD, ChannelE</td>
    </tr>
    <tr>
        <td>MilitaryStatus*</td>
        <td>string</td>
        <td colspan=2>true, false, null</td>
    </tr>
    <tr>
        <td>RNDegree*</td>
        <td>string</td>
        <td colspan=2>true, false, null</td>
    </tr>
    <tr>
        <td>StartDate*</td>
        <td>string</td>
        <td colspan=2>LESS_THAN_1_MONTH, 1_TO_3_MONTHS, 3_TO_6_MONTHS, 6_TO_12_MONTHS, OVER_12_MONTHS</td>
    </tr>
    <tr>
        <td>USCitizen*</td>
        <td>string</td>
        <td colspan=2>true, false, null</td>
    </tr>
    <tr>
        <td>Accreditations*</td>
        <td>string</td>
        <td colspan=2>Regionally Accredited, Nationally Accredited, Cacrep Accredited, Mpcac Accredited,  AACSB Accredited, AAPC Accredited, ABA Accredited, ABET Accredited, ABHES Accredited, ACBSP Accredited, ACCET Accredited, ACCJC Accredited, ACCSC Accredited, ACEN Accredited, ACEND Accredited, ACICS Accredited, ACOTE Accredited, ACPSP Accredited, AHIMA Accredited, APA Accredited, ARC-PA, Accredited ARRT Accredited, ASHA Accredited, CAAHEP Accredited, CAHIIM Accredited, CAHME Accredited, CCNE Accredited, CEPH Accredited, COAMFTE Accredited, COE Accredited, CSWE Accredited, DEAC Accredited, HLC Accredited, IACBE Accredited, Institutionally Accredited, MSCHE Accredited, NAACLS Accredited, NASAC Accredited, NASP Accredited, NASPAA Accredited, NAVTA Accredited, NEASC Accredited, NECHE Accredited, NLNAC Accredited, NWCCU Accredited, SACSCOC Accredited, SACSOC Accredited, WSCUC Accredited, CAEP Accredited, CACREP Adherence</td>
    </tr>
    <tr>
        <td>ProgramLength*</td>
        <td>string</td>
        <td colspan=2>1 Year Program, 2 Year Program, 18 Month Program, Accelerated, Advanced Standig Option</td>
    </tr>
    <tr>
        <td>ProgramRequirements*</td>
        <td>string</td>
        <td colspan=2>NO GRE, NO GMAT, NO APPLICATION FEE</td>
    </tr>
    <tr>
        <td>FName ±</td>
        <td>string</td>
	<td colspan=2></td>
    </tr>
    <tr>
        <td>LName ±</td>
        <td>string</td>
	<td colspan=2></td>
    </tr>
    <tr>
        <td>Email ±</td>
        <td>string</td>
	<td colspan=2></td>
    </tr>
    <tr>
        <td>Phone ±</td>
        <td>string</td>
	<td colspan=2></td>
    </tr>
    <tr>
        <td>Address ±</td>
        <td>string</td>
	<td colspan=2></td>
    </tr>
    <tr>
        <td>City ±</td>
        <td>string</td>
	<td colspan=2></td>
    </tr>
</table>


*Case Sensitive

** Program Ad Copy Allowed Values

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
