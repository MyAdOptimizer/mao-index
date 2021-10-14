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


<h3>Specific Query String Parameters for <strong>Education</strong></h3>

| Query String Params Names | Data Type | Allowed Values |
| :------------------------ | :-------: | :------------- |
| ZipCode                   | string    | 5 char US zip code               |
| State*                     | string    | 2 char US state code (Uppercase)    |
| AdPlacement               | string    | ICF, No Matches, After Matches, API, High School, Ad Unit, Organic Exit Pop, Paid Search Exit Pop | 
| AreaOfStudy*               | string    | Arts / Design / Fashion, Business, Communication & Multimedia, Computers & IT, Cosmetology & Beauty, Criminal Justice & Law Enforcement, Culinary Arts & Hospitality, Education & Teaching, General Studies / Undecided, Health & Medical / Nursing, Legal Professions, Massage Therapy & Healing Arts, Political Science, Psychology & Social Work, Religious Studies,Trades & Careers |
| Concentration*             | string    | Human Services/Social Work, Medical Assistant, Medical Insurance Biller/Coder, Medical Office Assistant, Medical Transcriptionist, Nursing - Licensed Practical/Vocational Nurse Training (Certificate), Nursing - MSN, Nursing - Registered Nurse (AAS), Nursing - RN to BSN, Nursing Assistant (CNA), Personal Training / Nutrition, Pharmacy Technician/Assistant, Phlebotomy / Clinical Medical Lab. Technician, Physical Therapy & Rehabilitation, Psychology, Surgical Technologist, Ultrasound Technician, Veterinary Medicine, X-Ray/Radiologic Technician, Court Reporting, Legal Administrative Assistant, Legal Assistant/Paralegal, Legal Studies, Healing Arts & Alternative Medicine, Massage Therapy, Political Science, Business & Organizational Psychology, Clinical Psychology, Counseling Psychology, Forensic Psychology/Crime Scene Investigator, General Psychology, Human Services/Social Work, Sport Psychology, Christian Studies, Ministry, Religious Studies, Theology, Aircraft Maintenance, Auto Mechanic, Autobody Repair, Aviation, CAD Drafting and Design, Computer Installation & Repair, Computer Systems Technology, Construction Management, Electrician, Engineering Technology/Technicians, HVAC, Laboratory Technician, Plumbing Technology/Plumber, Telecommunications Technology, Truck Driving, Welding Technology/Welder, Design & Visual Communications, Fashion/Apparel Design, Film and Theater, Graphic Design, Industrial Design, Interior Design, Photography, Visual Arts, Accounting & Related Services, Administrative & Secretarial Services, Business Communications, E-Commerce/Business, Economics, Entrepreneurship & Small Business, Fashion and Apparel, Finance, General Business, Green & Sustainable Management, Hospitality & Restaurants, Human Resources, Information Systems Management, International Business, Management, Marketing, Property Management / Real Estate, Public & Non-Profit Administration, Retail & Sales, Supply Chain Management, Advertising, Animation & Video Graphics, Commercial & Advertising Art, Computer Media Applications, Design & Visual Communications, Film/Video & Cinematography, Graphic Design, Intermedia/Multimedia, Photography, Recording Arts Technology, Web Design, Computer Science, Computer Support Services, Computer Systems Security, Networking, Software Development, Systems Administration, Telecommunications, Web Design and Internet, Barbering/Barber, Cosmetology/Cosmetologist, Esthetician & Skin Care, Hair Styling & Hair Design, Make-Up Artist/Specialist, Manicurist/Nail Specialist, Correctional Officer (Prison Officer), Criminal Justice & Law Enforcement/Police, Fire Science, Forensics/Crime Scene Investigation, Homeland Security, Security Services, Baking and Pastry Arts, Culinary Arts, Food Services, Hospitality Management, Restaurant & Food Services, Tourism & Travel Management, Administration & Leadership, Curriculum and Instruction, Early Childhood Education, Education and Teaching, General Education, Secondary Education, General Studies, Liberal Arts, Undecided, Alternative Medicine/Healing Arts, Dental Assisting, Dental Hygienist, Diagnostic & Treatment Technician, Gerontology, Health Information Technology/Records, Healthcare Administration |
| DegreeLevel*               | string    | CERTIFICATE, ASSOCIATES, BACHELORS, MASTERS, DOCTORATE |
| HighSchoolGradYear        | Integer   | 2020, 2019, 2018, 2017, 2016, 2015, 2014, 2013, 2012, 2011, 2010, 2009, 2008, 2007, 2006, 2005, 2004, 2003, 2002, 2001, 1990 |
| HighestEducationLevel*     | string    | STILL_IN_HIGH_SCHOOL, NO_HIGH_SCHOOL_OR_GED, HIGH_SCHOOL, SOME_COLLEGE, ASSOCIATES_DEGREE, BACHELORS_DEGREE, MASTERS_DEGREE, DOCTORAL_DEGREE, GED |
| LearningPreference*        | string    | CAMPUS, ONLINE, HYBRID, ANY |
| LikelihoodToEnroll*        | string    | NOT_LIKELY, SOMEWHAT_LIKELY, VERY_LIKELY |
| MilitaryStatus*            | string    | true, false, null |
| RNDegree*                  | string    | true, false, null |
| StartDate*                 | string    | LESS_THAN_1_MONTH, 1_TO_3_MONTHS, 3_TO_6_MONTHS, 6_TO_12_MONTHS, OVER_12_MONTHS |
| USCitizen*                 | string    | true, false, null |
| Accreditations*             | string    | Regionally Accredited, Nationally Accredited, Cacrep Accredited, Mpcac Accredited | 
| ProgramLength*             | string    | 1 Year Program, 2 Year Program, 18 Month Program, Accelerated, Advanced Standig Option | 
| Requirements*              | string    | No GRE, No GMAT |

*Case Sensitive

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
    "searchResultId": "acbb214a-e69e-4394-bea0-3b48f6997cca",
    "duration": 446,
    "items": [
        {
            "itemId": "458",
            "brandName": "Florida Career College",
            "networkSort": 1,
            "requestDuration": 306,
            "sourceID": null,
            "extClickID": "testClickID",
            "advertiserId": "409",
            "displayName": "Earn A Business Office Administration Diploma - Start Building A Future You Can Be Proud Of",
            "headline": "Learn valuable technical skills like - Microsoft Word&#174;, Microsoft Excel&#174;, Microsoft PowerPoint&#174; and more!&lt;br /&gt;Prepare for career opportunities like: Administrative Assistant, Secretary, Customer Service Rep, and more!&lt;br /&gt;Fast: Prepare for a career in as few as 10 months&lt;br /&gt;Convenient: Daytime and evening classes available",
            "blurbs": [
                "Learn valuable technical skills like - Microsoft Word®, Microsoft Excel®, Microsoft PowerPoint® and more!",
                "Prepare for career opportunities like: Administrative Assistant, Secretary, Customer Service Rep, and more!",
                "Fast: Prepare for a career in as few as 10 months",
                "Convenient: Daytime and evening classes available",
                "Helpful: Financial Aid available to those who qualify"
            ],
            "programAdCopy": {
                "customVar": [
                    {
                        "element": "Institution",
                        "items": [
                            {
                                "item": "Public",
                                "value": true
                            },
                            {
                                "item": "Private",
                                "value": false
                            }
                        ]
                    },
                    {
                        "element": "Profit",
                        "items": [
                            {
                                "item": "Non-Profit",
                                "value": true
                            },
                            {
                                "item": "For-Profit",
                                "value": false
                            },
                            {
                                "item": "Not-For-Profit",
                                "value": false
                            }
                        ]
                    },
                    {
                        "element": "Enrollement",
                        "items": [
                            {
                                "item": "> 50K",
                                "value": true
                            },
                            {
                                "item": "30K - 50K",
                                "value": false
                            },
                            {
                                "item": "15K - 30K",
                                "value": false
                            },
                            {
                                "item": "5K - 15K",
                                "value": false
                            },
                            {
                                "item": "< 5K",
                                "value": false
                            }
                        ]
                    }
                ],
                "location": "Location",
                "advertiserName": "Advertiser Name",
                "programName": "Program Name",
                "programDescription": "Program Description"
            },
            "imageUrl": "https://cdn.myadoptimizer.com/maojsfiles/images/LogoAdvertiser_000458_52ce13ea-5a04-42cc-8c44-919677e99f04.jpg",
            "destUrl": "https://api.myadoptimizer.com/api/MAOHttpRedirect?src=https%3A%2F%2Finfo.floridacareercollege.com%2Fbusiness-office-administration%2F%3Fadkey%3DIS1CAEXN00%26ctc%3D877-425-6149%26utm_source%3Dcexplorer%26utm_medium%3Dcpc%26utm_campaign060118-fcc-cpc%26utm_content%3DFCC-Business%26CCK%3Dacbb214a-e69e-4394-bea0-3b48f6997cca%7Cfcc_business%26t%3DtestClickID&LandingPageID=43&EventID=acbb214a-e69e-4394-bea0-3b48f6997cca&AdNetworkAPIID=44&cpc=34.50&Brand=Florida Career College&Title=Earn A Business Office Administration Diploma - Start Building A Future You Can Be Proud Of&CB=1VawjEjip8ij5oaSZJZ0mw==&M=4XarSvqYDCayCqZpzLZFSg==&Weight=34.50&BidModifiers=50.00&NetworkAdID=458&SourceID=&LandingPageURL=",
            "impressionUrl": "https://api.myadoptimizer.com/api/MAOSaveResults?LandingPageID=43&AdNetworkAPIID=44&EventID=acbb214a-e69e-4394-bea0-3b48f6997cca&AdCampaignID=458&RequestTypeID=4",
            "revenue": 34.50,
            "baseRevenue": 23.00,
            "isOnlineSchool": null,
            "schoolAddress": "",
            "schoolCity": "",
            "schoolState": "",
            "schoolZipCode": "",
            "bidModifierLog": [
              "Ad Placement: ICF - Value: 50.00%",
              "States: PA - Value: -10.00%",
              "Tuesday: 14:40 - Value: 10.00%"
            ],
            "weight": 34.50,
            "statusId": 1,
            "trackingURL": "https://api.myadoptimizer.com/api/MAOLeadTracking?AdNetworkAPIID=44&LandingPageID=43&EventID=acbb214a-e69e-4394-bea0-3b48f6997cca&IP=123.32.32.123&AdCampaignID=458",
            "displayUrl": "http://www.floridacareercollege.com/business-office-administration"
        }
    ]
}
```


## Program Ad Copy

Response example for campaigns with **program ad copy** configured:

```JSON
"programAdCopy": {
                "customVar": [
                    {
                        "element": "Institution",
                        "items": [
                            {
                                "item": "Public",
                                "value": true
                            },
                            {
                                "item": "Private",
                                "value": false
                            }
                        ]
                    },
                    {
                        "element": "Profit",
                        "items": [
                            {
                                "item": "Non-Profit",
                                "value": true
                            },
                            {
                                "item": "For-Profit",
                                "value": false
                            },
                            {
                                "item": "Not-For-Profit",
                                "value": false
                            }
                        ]
                    },
                    {
                        "element": "Enrollement",
                        "items": [
                            {
                                "item": "> 50K",
                                "value": true
                            },
                            {
                                "item": "30K - 50K",
                                "value": false
                            },
                            {
                                "item": "15K - 30K",
                                "value": false
                            },
                            {
                                "item": "5K - 15K",
                                "value": false
                            },
                            {
                                "item": "< 5K",
                                "value": false
                            }
                        ]
                    }
                ],
                "location": "Location",
                "advertiserName": "Advertiser Name",
                "programName": "Program Name",
                "programDescription": "Program Description"
            },

```

Response example for campaigns with **program ad copy** not configured:

```JSON
 "programAdCopy": {
                "customVar": [
                    null,
                    null,
                    null
                ],
                "location": "",
                "advertiserName": "",
                "programName": "",
                "programDescription": ""
            },
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
