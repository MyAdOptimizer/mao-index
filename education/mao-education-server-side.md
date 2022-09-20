<p align="center">
  <a href="https://myadoptimizer.com/">
    <img src="https://myadoptimizer.com/img/logo-blk.svg" alt="Logo" height="80">
  </a>
  <h3 align="center">MyAdOptimizer.com Server API Integration Doc | Education</h3>
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
    * [Specific Query String Parameters for Education](#specific-query-string-parameters-for-education)
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
* SourceID: `Optional, tracking variable to be used at your convenience. MAO will track it and can be used for custom reporting `
* ExtClickID: `Optional, tracking variable to be used at your convenience. MAO will track it and can be used for custom reporting `
* ExtSearchID: `Optional, tracking variable to be used at your convenience. MAO will track it and can be used for custom reporting `
* UserAgent: `Optional,  Mozilla/<version> (<system-information>) <platform> (<platform-details>) <extensions>`
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
        <td colspan=2>5 char US zip code</td>
    </tr>
    <tr>
        <td>State*</td>
        <td>string</td>
        <td colspan=2 >2 char US code (Uppercase)</td>
    </tr>
    <tr>
        <td>AdPlacement*</td>
        <td>string</td>
        <td colspan=2 >ICF, No Matches, After Matches, API, High School, Ad Unit, Organic Exit Pop, Paid Search Exit Pop</td>
    </tr>
    <tr>
        <td>AreaOfStudy* </td>
        <td>String</td>
        <td colspan=2>
            Arts / Design / Fashion, Business, Communication & Multimedia, Computers & IT, Cosmetology & Beauty, Criminal Justice & Law Enforcement, Culinary Arts & Hospitality, Education & Teaching, General Studies / Undecided, Health & Medical / Nursing, Legal
            Professions, Massage Therapy & Healing Arts, Political Science, Psychology & Social Work, Religious Studies,Trades & Careers, Counseling
        </td>
    </tr>
    <tr>
        <td rowspan=18> Concentration*</td>
        <td rowspan=18> string </td>
        <td> Arts / Design / Fashion </td>
        <td>Design & Visual Communications, Fashion/Apparel Design, Film and Theater, Graphic Design, Industrial Design, Interior Design, Photography, Visual Arts</td>
    </tr>
    <tr>
        <td>Business</td>
        <td>
            Accounting & Related Services, Administrative & Secretarial Services, Business Communications, E-Commerce/Business, Economics, Entrepreneurship & Small Business, Fashion and Apparel, Finance, General Business, Green & Sustainable Management, Hospitality
            & Restaurants, Human Resources, Information Systems Management, International, Business, Management, Marketing, Property Management / Real Estate, Public & Non-Profit Administration, Retail & Sales, Supply Chain Management, Business Administration, Business Intelligence, Organizational Leadership, Project Management, Taxation
        </td>
    </tr>
    <tr>
        <td>Communication & Multimedia</td>
        <td>
            Advertising, Animation & Video Graphics, Commercial & Advertising Art, Computer Media Applications, Design & Visual Communications, Film/Video & Cinematography, Graphic Design, Intermedia/Multimedia, Photography, Recording Arts Technology, Web
            Design
        </td>
    </tr>
    <tr>
        <td>Computers & IT</td>
        <td>
            Computer Science, Computer Support Services, Computer Systems Security, Networking, Software Development, Systems Administration, Telecommunications, Web Design and Internet, Analytics & Data Science, Engineering, Information & Library Sciences, Information Technology/Systems
        </td>
    </tr>
    <tr>
        <td>Cosmetology & Beauty</td>
        <td>
            Barbering/Barber, Cosmetology/Cosmetologist, Esthetician & Skin Care, Hair Styling & Hair Design, Make-Up Artist/Specialist, Manicurist/Nail Specialist
        </td>
    </tr>
    <tr>
        <td>Criminal Justice & Law Enforcement</td>
        <td>
            Correctional Officer (Prison Officer), Criminal Justice & Law Enforcement/Police, Fire Science, Forensics/Crime Scene Investigation, Homeland Security, Security Services,
            Criminal Justice, Criminology
        </td>
    </tr>
    <tr>
        <td>Culinary Arts & Hospitality</td>
        <td>Baking and Pastry Arts, Culinary Arts, Food Services, Hospitality Management, Restaurant & Food Services, Tourism & Travel Management</td>
    </tr>
    <tr>
        <td>Education & Teaching</td>
        <td>
            Administration & Leadership, Curriculum and Instruction, Early Childhood Education, Education and Teaching, General Education, Secondary Education, Educational Technology, Elementary Education, Music Education, Reading & Literacy, Special Education, Teaching
        </td>
    </tr>
    <tr>
        <td>General Studies / Undecided</td>
        <td>General Studies, Liberal Arts, Undecided</td>
    </tr>
    <tr>
        <td>Health & Medical / Nursing</td>
        <td>
            Alternative Medicine/Healing Arts, Dental Assisting, Dental Hygienist, Diagnostic & Treatment Technician, Gerontology, Health Information Technology/Records, Healthcare Administration, Human Services/Social Work, Medical Assistant, Medical Insurance Biller/Coder, Medical Office Assistant, Medical Transcriptionist, Nursing - Licensed Practical/Vocational Nurse Training (Certificate), Nursing - MSN, Nursing - Registered Nurse (AAS), Nursing - RN to BSN, Nursing Assistant (CNA), Personal Training / Nutrition, Pharmacy Technician/Assistant, Phlebotomy / Clinical Medical Lab. Technician, Physical Therapy & Rehabilitation, Psychology, Surgical Technologist, Ultrasound Technician, Veterinary Medicine, X-Ray/Radiologic Technician, Emergency Management, Nurse Education, Nurse Practitioner (RN Required), Public Health, Speech Pathology/Therapy
        </td>
    </tr>
    <tr>
        <td>Legal Professions</td>
        <td>Court Reporting, Legal Administrative Assistant, Legal Assistant/Paralegal, Legal Studies</td>
    </tr>
    <tr>
        <td>Massage Therapy & Healing Arts</td>
        <td>Healing Arts & Alternative Medicine, Massage Therapy</td>
    </tr>
    <tr>
        <td>Political Science</td>
        <td>Political Science</td>
    </tr>
    <tr>
        <td>Psychology & Social Work</td>
        <td>
            Business & Organizational Psychology, Clinical Psychology, Counseling Psychology, Forensic Psychology/Crime Scene Investigator, General Psychology, Human Services/Social Work, Sport Psychology, Behavioral Psychology, Child Psychology, Educational Psychology
        </td>
    </tr>
    <tr>
        <td>Religious Studies</td>
        <td>Christian Studies, Ministry, Religious Studies, Theology</td>
    </tr>
    <tr>
        <td>Trades & Careers</td>
        <td>Aircraft Maintenance, Auto Mechanic, Autobody Repair, Aviation, CAD Drafting and Design, Computer Installation & Repair, Computer Systems Technology, Construction Management, Electrician, Engineering Technology/Technicians, HVAC, Laboratory Technician, Plumbing Technology/Plumber, Telecommunications Technology, Truck Driving, Welding Technology/Welder</td>
    </tr>
    <tr>
        <td>Counseling</td>
        <td>Addictions & Recovery, Counseling, Family Counseling, Mental Health Counseling, School Counseling</td>
    </tr>
<tr>
    </tr>
    <tr>
        <td>DegreeLevel*</td>
        <td>string</td>
        <td colspan=2>CERTIFICATE, ASSOCIATES, BACHELORS, MASTERS, DOCTORATE</td>
    </tr>
    <tr>
        <td>HighSchoolGradYear</td>
        <td>string</td>
        <td colspan=2>2020, 2019, 2018, 2017, 2016, 2015, 2014, 2013, 2012, 2011, 2010, 2009, 2008, 2007, 2006, 2005, 2004, 2003, 2002, 2001, 1990</td>
    </tr>
    <tr>
        <td>HighestEducationLevel*</td>
        <td>string</td>
        <td colspan=2 >STILL_IN_HIGH_SCHOOL, NO_HIGH_SCHOOL_OR_GED, HIGH_SCHOOL, SOME_COLLEGE, ASSOCIATES_DEGREE, BACHELORS_DEGREE, MASTERS_DEGREE, DOCTORAL_DEGREE, GED</td>
    </tr>
    <tr>
        <td>LearningPreference*</td>
        <td>string</td>
        <td colspan=2>CAMPUS, ONLINE, BOTH</td>
    </tr>
    <tr>
        <td>LikelihoodToEnroll*</td>
        <td>string</td>
        <td colspan=2>NOT_LIKELY, SOMEWHAT_LIKELY, VERY_LIKELY</td>
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

### API Response

* destURL: `This is the Click URL. Please use the value from this field when a click is triggered.`
* impressionUrl: `This is a call back URL so that MAO can track live impressions. If a listing is displayed in your result set, please trigger the impressionUrl of  that listing`
* displayUrl: `This is the value from “Display URL” in the Campaign Ad Copy `
* trackingURL: `This is a Image Pixel to track leads or form submits from Clicks. This is optional to implement, but it is used to provide traceability from a click to a lead submit`
* revenue: `Actual payout per click based on bid modifiers.`
* baseRevenue: `Base bid per click. It'll vary based on bid modifiers.`
* bidModifierLog: `The log that shows  how the baseRevenue bid was modified.`

Example response:

```JSON
{
   "searchResultId":"acbb214a-e69e-4394-bea0-3b48f6997cca",
   "duration":446,
   "items":[
      {
         "itemId":"458",
         "brandName":"Florida Career College",
         "networkSort":1,
         "requestDuration":306,
         "sourceID":null,
         "extClickID":"testClickID",
         "advertiserId":"409",
         "displayName":"Earn A Business Office Administration Diploma - Start Building A Future You Can Be Proud Of",
         "adCopyVersion":1,
         "headline":"Learn valuable technical skills like - Microsoft Word&#174;, Microsoft Excel&#174;, Microsoft PowerPoint&#174; and more!&lt;br /&gt;Prepare for career opportunities like: Administrative Assistant, Secretary, Customer Service Rep, and more!&lt;br /&gt;Fast: Prepare for a career in as few as 10 months&lt;br /&gt;Convenient: Daytime and evening classes available",
         "blurbs":[
            "Learn valuable technical skills like - Microsoft Word®, Microsoft Excel®, Microsoft PowerPoint® and more!",
            "Prepare for career opportunities like: Administrative Assistant, Secretary, Customer Service Rep, and more!",
            "Fast: Prepare for a career in as few as 10 months",
            "Convenient: Daytime and evening classes available",
            "Helpful: Financial Aid available to those who qualify"
         ],
         "programAdCopy":{
            "customVar":[
               null,
               null,
               null
            ],
            "constraints":[
               
            ],
            "location":"",
            "advertiserName":"",
            "programName":"",
            "programDescription":"",
            "imageUrl":""
         },
         "imageUrl":"https://cdn.myadoptimizer.com/maojsfiles/images/LogoAdvertiser_000458_52ce13ea-5a04-42cc-8c44-919677e99f04.jpg",
         "destUrl":"https://api.myadoptimizer.com/api/MAOHttpRedirect?src=https%3A%2F%2Finfo.floridacareercollege.com%2Fbusiness-office-administration%2F%3Fadkey%3DIS1CAEXN00%26ctc%3D877-425-6149%26utm_source%3Dcexplorer%26utm_medium%3Dcpc%26utm_campaign060118-fcc-cpc%26utm_content%3DFCC-Business%26CCK%3Dacbb214a-e69e-4394-bea0-3b48f6997cca%7Cfcc_business%26t%3DtestClickID&LandingPageID=43&EventID=acbb214a-e69e-4394-bea0-3b48f6997cca&AdNetworkAPIID=44&cpc=34.50&Brand=Florida Career College&Title=Earn A Business Office Administration Diploma - Start Building A Future You Can Be Proud Of&CB=1VawjEjip8ij5oaSZJZ0mw==&M=4XarSvqYDCayCqZpzLZFSg==&Weight=34.50&BidModifiers=50.00&NetworkAdID=458&SourceID=&LandingPageURL=",
         "impressionUrl":"https://api.myadoptimizer.com/api/MAOSaveResults?LandingPageID=43&AdNetworkAPIID=44&EventID=acbb214a-e69e-4394-bea0-3b48f6997cca&AdCampaignID=458&RequestTypeID=4",
         "revenue":34.5,
         "baseRevenue":23.0,
         "isOnlineSchool":null,
         "schoolAddress":"",
         "schoolCity":"",
         "schoolState":"",
         "schoolZipCode":"",
         "bidModifierLog":[
            "Ad Placement: ICF - Value: 50.00%",
            "States: PA - Value: -10.00%",
            "Tuesday: 14:40 - Value: 10.00%"
         ],
         "weight":34.5,
         "statusId":1,
         "trackingURL":"https://api.myadoptimizer.com/api/MAOLeadTracking?AdNetworkAPIID=44&LandingPageID=43&EventID=acbb214a-e69e-4394-bea0-3b48f6997cca&IP=123.32.32.123&AdCampaignID=458",
         "displayUrl":"http://www.floridacareercollege.com/business-office-administration"
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
