<p align="center">
  <a href="https://myadoptimizer.com/">
    <img src="https://myadoptimizer.com/img/logo-blk.svg" alt="Logo" height="80">
  </a>
  <h3 align="center">MyAdOptimizer.com Server API Integration Doc | Education</h3>
  <p align="center">
    Learn how to integrate the <strong>MAO Server API (Listings Mode)</strong> by following these steps
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
        <td colspan=2 > Program Listings - Widget, Program  Listings - Static </td>
    </tr>
    <tr>
        <td>AreaOfStudy* </td>
        <td>String</td>
        <td colspan=2>
            Arts / Design / Fashion, Business, Communication & Multimedia, Computers & IT, Cosmetology & Beauty, Criminal Justice & Law Enforcement, Culinary Arts & Hospitality, Education & Teaching, General Studies / Undecided, Health & Medical / Nursing, Legal
            Professions, Massage Therapy & Healing Arts, Political Science, Psychology & Social Work, Religious Studies,Trades & Careers, Counseling, ANY
        </td>
    </tr>
    <tr>
        <td rowspan=18> Concentration*</td>
        <td rowspan=18> string </td>
        <td> Arts / Design / Fashion </td>
        <td>Design & Visual Communications, Fashion/Apparel Design, Film and Theater, Graphic Design, Industrial Design, Interior Design, Photography, Visual Arts, ANY</td>
    </tr>
    <tr>
        <td>Business</td>
        <td>
            Accounting & Related Services, Administrative & Secretarial Services, Business Communications, E-Commerce/Business, Economics, Entrepreneurship & Small Business, Fashion and Apparel, Finance, General Business, Green & Sustainable Management, Hospitality
            & Restaurants, Human Resources, Information Systems Management, International, Business, Management, Marketing, Property Management / Real Estate, Public & Non-Profit Administration, Retail & Sales, Supply Chain Management, Business Administration, Business Intelligence, Organizational Leadership, Project Management, Taxation, ANY
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
            Computer Science, Computer Support Services, Computer Systems Security, Networking, Software Development, Systems Administration, Telecommunications, Web Design and Internet, Analytics & Data Science, Engineering, Information & Library Sciences, Information Technology/Systems, ANY
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
        <td>General Studies, Liberal Arts, Undecided, ANY</td>
    </tr>
    <tr>
        <td>Health & Medical / Nursing</td>
        <td>
            Alternative Medicine/Healing Arts, Dental Assisting, Dental Hygienist, Diagnostic & Treatment Technician, Gerontology, Health Information Technology/Records, Healthcare Administration, Human Services/Social Work, Medical Assistant, Medical Insurance Biller/Coder, Medical Office Assistant, Medical Transcriptionist, Nursing - Licensed Practical/Vocational Nurse Training (Certificate), Nursing - MSN, Nursing - Registered Nurse (AAS), Nursing - RN to BSN, Nursing Assistant (CNA), Personal Training / Nutrition, Pharmacy Technician/Assistant, Phlebotomy / Clinical Medical Lab. Technician, Physical Therapy & Rehabilitation, Psychology, Surgical Technologist, Ultrasound Technician, Veterinary Medicine, X-Ray/Radiologic Technician, Emergency Management, Nurse Education, Nurse Practitioner (RN Required), Public Health, Speech Pathology/Therapy, ANY
        </td>
    </tr>
    <tr>
        <td>Legal Professions</td>
        <td>Court Reporting, Legal Administrative Assistant, Legal Assistant/Paralegal, Legal Studies, ANY</td>
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
        <td colspan=2>CERTIFICATE, ASSOCIATES, BACHELORS, MASTERS, DOCTORATE, ANY</td>
    </tr>
    <tr>
        <td>LearningPreference*</td>
        <td>string</td>
        <td colspan=2>CAMPUS, ONLINE, HYBRID</td>
    </tr>
    <tr>
        <td>Accreditations*</td>
        <td>string</td>
        <td colspan=2>Regionally Accredited, Nationally Accredited, Cacrep Accredited, Mpcac Accredited,  AACSB Accredited, AAPC Accredited, ABA Accredited, ABET Accredited, ABHES Accredited, ACBSP Accredited, ACCET Accredited, ACCJC Accredited, ACCSC Accredited, ACEN Accredited, ACEND Accredited, ACICS Accredited, ACOTE Accredited, ACPSP Accredited, AHIMA Accredited, APA Accredited, ARC-PA, Accredited ARRT Accredited, ASHA Accredited, CAAHEP Accredited, CAHIIM Accredited, CAHME Accredited, CCNE Accredited, CEPH Accredited, COAMFTE Accredited, COE Accredited, CSWE Accredited, DEAC Accredited, HLC Accredited, IACBE Accredited, Institutionally Accredited, MSCHE Accredited, NAACLS Accredited, NASAC Accredited, NASP Accredited, NASPAA Accredited, NAVTA Accredited, NEASC Accredited, NECHE Accredited, NLNAC Accredited, NWCCU Accredited, SACSCOC Accredited, SACSOC Accredited, WSCUC Accredited</td>
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

### API Response

* destURL: `This is the Click URL. Please use the value from this field when a click is triggered.`
* impressionUrl: `This is a call back URL so that MAO can track live impressions. If a listing is displayed in your result set, please trigger the impressionUrl of  that listing`
* trackingURL: `This is a Image Pixel to track leads or form submits from Clicks. This is optional to implement, but it is used to provide traceability from a click to a lead submit`
* revenue: `Actual payout per click based on bid modifiers.`
* baseRevenue: `Base bid per click. It'll vary based on bid modifiers.`
* bidModifierLog: `The log that shows  how the baseRevenue bid was modified.`

Example response:

```JSON
{
   "searchResultId":"000xx000-00xx-0xx0-x0xx-000000x0000x",
   "duration":198,
   "items":[
      {
         "itemId":"2196",
         "brandName":"Advertiser Brand 2022 09 19 13.06",
         "networkSort":1,
         "requestDuration":278,
         "sourceID":null,
         "extClickID":null,
         "advertiserId":"906",
         "displayName":"Campaign 2022 09 19 13.06",
         "adCopyVersion":1,
         "headline":"",
         "blurbs":[
            
         ],
         "programAdCopy":{
            "customVar":[
               {
                  "element":"Institution",
                  "items":[
                     {
                        "item":"Public",
                        "value":true
                     }
                  ]
               },
               {
                  "element":"Profit",
                  "items":[
                     {
                        "item":"Non-Profit",
                        "value":true
                     }
                  ]
               },
               {
                  "element":"Enrollment",
                  "items":[
                     {
                        "item":"> 50K Students",
                        "value":true
                     }
                  ]
               },
               {
                  "element":"Benefits",
                  "items":[
                     {
                        "item":"Flexible Schedules",
                        "value":true
                     }
                  ]
               }
            ],
            "constraints":[
               {
                  "element":"Accreditations",
                  "items":[
                     {
                        "item":"Regionally Accredited",
                        "value":true
                     },
                     {
                        "item":"Nationally Accredited",
                        "value":true
                     },
                     {
                        "item":"CACREP Accredited",
                        "value":true
                     },
                     {
                        "item":"MPCAC Accredited",
                        "value":true
                     },
                     {
                        "item":"AACSB Accredited",
                        "value":true
                     },
                     {
                        "item":"AAPC Accredited",
                        "value":true
                     },
                     {
                        "item":"ABA Accredited",
                        "value":true
                     },
                     {
                        "item":"ABET Accredited",
                        "value":true
                     },
                     {
                        "item":"ABHES Accredited",
                        "value":true
                     },
                     {
                        "item":"ACBSP Accredited",
                        "value":true
                     },
                     {
                        "item":"ACCET Accredited",
                        "value":true
                     },
                     {
                        "item":"ACCJC Accredited",
                        "value":true
                     },
                     {
                        "item":"ACCSC Accredited",
                        "value":true
                     },
                     {
                        "item":"ACEN Accredited",
                        "value":true
                     },
                     {
                        "item":"ACEND Accredited",
                        "value":true
                     },
                     {
                        "item":"ACICS Accredited",
                        "value":true
                     },
                     {
                        "item":"ACOTE Accredited",
                        "value":true
                     },
                     {
                        "item":"ACPSP Accredited",
                        "value":true
                     },
                     {
                        "item":"AHIMA Accredited",
                        "value":true
                     },
                     {
                        "item":"APA Accredited",
                        "value":true
                     },
                     {
                        "item":"ARC-PA Accredited",
                        "value":true
                     },
                     {
                        "item":"ARRT Accredited",
                        "value":true
                     },
                     {
                        "item":"ASHA Accredited",
                        "value":true
                     },
                     {
                        "item":"CAAHEP Accredited",
                        "value":true
                     },
                     {
                        "item":"CAHIIM Accredited",
                        "value":true
                     },
                     {
                        "item":"CAHME Accredited",
                        "value":true
                     },
                     {
                        "item":"CCNE Accredited",
                        "value":true
                     },
                     {
                        "item":"CEPH Accredited",
                        "value":true
                     },
                     {
                        "item":"COAMFTE Accredited",
                        "value":true
                     },
                     {
                        "item":"COE Accredited",
                        "value":true
                     },
                     {
                        "item":"CSWE Accredited",
                        "value":true
                     },
                     {
                        "item":"DEAC Accredited",
                        "value":true
                     },
                     {
                        "item":"HLC Accredited",
                        "value":true
                     },
                     {
                        "item":"IACBE Accredited",
                        "value":true
                     },
                     {
                        "item":"Institutionally Accredited",
                        "value":true
                     },
                     {
                        "item":"MSCHE Accredited",
                        "value":true
                     },
                     {
                        "item":"NAACLS Accredited",
                        "value":true
                     },
                     {
                        "item":"NASAC Accredited",
                        "value":true
                     },
                     {
                        "item":"NASP Accredited",
                        "value":true
                     },
                     {
                        "item":"NASPAA Accredited",
                        "value":true
                     },
                     {
                        "item":"NAVTA Accredited",
                        "value":true
                     },
                     {
                        "item":"NEASC Accredited",
                        "value":true
                     },
                     {
                        "item":"NECHE Accredited",
                        "value":true
                     },
                     {
                        "item":"NLNAC Accredited",
                        "value":true
                     },
                     {
                        "item":"NWCCU Accredited",
                        "value":true
                     },
                     {
                        "item":"SACSCOC Accredited",
                        "value":true
                     },
                     {
                        "item":"SACSOC Accredited",
                        "value":true
                     },
                     {
                        "item":"WSCUC Accredited",
                        "value":true
                     }
                  ]
               },
               {
                  "element":"Program Requirements",
                  "items":[
                     {
                        "item":"NO APPLICATION FEE",
                        "value":true
                     },
                     {
                        "item":"NO GRE",
                        "value":true
                     },
                     {
                        "item":"NO GMAT",
                        "value":true
                     }
                  ]
               },
               {
                  "element":"Program Length",
                  "items":[
                     {
                        "item":"1 Year Program",
                        "value":true
                     },
                     {
                        "item":"2 Year Program",
                        "value":true
                     },
                     {
                        "item":"18 Month Program",
                        "value":true
                     },
                     {
                        "item":"Accelerated",
                        "value":true
                     },
                     {
                        "item":"Advanced Standing Option",
                        "value":true
                     }
                  ]
               }
            ],
            "location":"Location",
            "advertiserName":"Advertiser Name",
            "programName":"Program Name",
            "programDescription":"Program Description",
            "imageUrl":"https://cdn.myadoptimizer.com/maojsfiles/images/ProgramAdCopyLogo_000000_d000ac0d-a00f-000-0ba0-0a0b0yz00000.png"
         },
         "imageUrl":"https://cdn.myadoptimizer.com/maojsfiles/images/",
         "destUrl":"https://maofunctionstest.azurewebsites.net/api/MAOHttpRedirect?src=Url+LInk&LandingPageID=64&EventID=000xx000-00xx-0xx0-x0xx-000000x0000x&AdNetworkAPIID=00&cpc=20.00&Brand=Advertiser Brand 2022 09 19 13.06&Title=&CB=abzOlnZByX2cFuqz9Mq5AQ==&M=4XarSvqYDCayCqZpzLZFSg==&Weight=20.00&BidModifiers=0&NetworkAdID=2196&SourceID=&LandingPageURL=&AdId=906&AdCopyVersion=1&CustomVar1=&CustomVar2=&CustomVar3=&CustomVar4=&CustomVar5=",
         "impressionUrl":"https://maofunctionstest.azurewebsites.net/api/MAOSaveResults?LandingPageID=00&AdNetworkAPIID=44&EventID=000xx000-00xx-0xx0-x0xx-000000x0000x&AdCampaignID=2196&RequestTypeID=4",
         "revenue":20.00,
         "cb":"abzOlnZByX2cFuqz9Mq5AQ==",
         "m":"4XarSvqYDCayCqZpzLZFSg==",
         "baseRevenue":20.00,
         "isOnlineSchool":false,
         "schoolAddress":"",
         "schoolCity":"",
         "schoolState":"",
         "schoolZipCode":"",
         "bidModifierLog":[
            
         ],
         "bidModifierPercentange":null,
         "weight":20.00,
         "statusId":1,
         "trackingURL":"https://maofunctionstest.azurewebsites.net/api/MAOLeadTracking?AdNetworkAPIID=44&LandingPageID=64&EventID=000xx000-00xx-0xx0-x0xx-000000x0000x&IP=50.162.168.1&AdCampaignID=2196",
         "displayUrl":"",
         "network":"MyAdOptimizer",
         "extSearchID":null,
         "customVar1":"",
         "customVar2":"",
         "customVar3":"",
         "customVar4":"",
         "customVar5":""
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
                            }
                        ]
                    },
                    {
                        "element": "Profit",
                        "items": [
                            {
                                "item": "Non-Profit",
                                "value": true
                            }
                        ]
                    },
                    {
                        "element": "Enrollment",
                        "items": [
                            {
                                "item": "> 50K Students",
                                "value": true
                            }
                        ]
                    },
                    {
                        "element": "Benefits",
                        "items": [
                            {
                                "item": "Flexible Schedules",
                                "value": true
                            }
                        ]
                    }
                ],
                "constraints": [
                    {
                        "element": "Accreditations",
                        "items": [
                            {
                                "item": "Regionally Accredited",
                                "value": true
                            },
                            {
                                "item": "Nationally Accredited",
                                "value": true
                            },
                            {
                                "item": "CACREP Accredited",
                                "value": true
                            },
                            {
                                "item": "MPCAC Accredited",
                                "value": true
                            },
                            {
                                "item": "AACSB Accredited",
                                "value": true
                            },
                            {
                                "item": "AAPC Accredited",
                                "value": true
                            },
                            {
                                "item": "ABA Accredited",
                                "value": true
                            },
                            {
                                "item": "ABET Accredited",
                                "value": true
                            },
                            {
                                "item": "ABHES Accredited",
                                "value": true
                            },
                            {
                                "item": "ACBSP Accredited",
                                "value": true
                            },
                            {
                                "item": "ACCET Accredited",
                                "value": true
                            },
                            {
                                "item": "ACCJC Accredited",
                                "value": true
                            },
                            {
                                "item": "ACCSC Accredited",
                                "value": true
                            },
                            {
                                "item": "ACEN Accredited",
                                "value": true
                            },
                            {
                                "item": "ACEND Accredited",
                                "value": true
                            },
                            {
                                "item": "ACICS Accredited",
                                "value": true
                            },
                            {
                                "item": "ACOTE Accredited",
                                "value": true
                            },
                            {
                                "item": "ACPSP Accredited",
                                "value": true
                            },
                            {
                                "item": "AHIMA Accredited",
                                "value": true
                            },
                            {
                                "item": "APA Accredited",
                                "value": true
                            },
                            {
                                "item": "ARC-PA Accredited",
                                "value": true
                            },
                            {
                                "item": "ARRT Accredited",
                                "value": true
                            },
                            {
                                "item": "ASHA Accredited",
                                "value": true
                            },
                            {
                                "item": "CAAHEP Accredited",
                                "value": true
                            },
                            {
                                "item": "CAHIIM Accredited",
                                "value": true
                            },
                            {
                                "item": "CAHME Accredited",
                                "value": true
                            },
                            {
                                "item": "CCNE Accredited",
                                "value": true
                            },
                            {
                                "item": "CEPH Accredited",
                                "value": true
                            },
                            {
                                "item": "COAMFTE Accredited",
                                "value": true
                            },
                            {
                                "item": "COE Accredited",
                                "value": true
                            },
                            {
                                "item": "CSWE Accredited",
                                "value": true
                            },
                            {
                                "item": "DEAC Accredited",
                                "value": true
                            },
                            {
                                "item": "HLC Accredited",
                                "value": true
                            },
                            {
                                "item": "IACBE Accredited",
                                "value": true
                            },
                            {
                                "item": "Institutionally Accredited",
                                "value": true
                            },
                            {
                                "item": "MSCHE Accredited",
                                "value": true
                            },
                            {
                                "item": "NAACLS Accredited",
                                "value": true
                            },
                            {
                                "item": "NASAC Accredited",
                                "value": true
                            },
                            {
                                "item": "NASP Accredited",
                                "value": true
                            },
                            {
                                "item": "NASPAA Accredited",
                                "value": true
                            },
                            {
                                "item": "NAVTA Accredited",
                                "value": true
                            },
                            {
                                "item": "NEASC Accredited",
                                "value": true
                            },
                            {
                                "item": "NECHE Accredited",
                                "value": true
                            },
                            {
                                "item": "NLNAC Accredited",
                                "value": true
                            },
                            {
                                "item": "NWCCU Accredited",
                                "value": true
                            },
                            {
                                "item": "SACSCOC Accredited",
                                "value": true
                            },
                            {
                                "item": "SACSOC Accredited",
                                "value": true
                            },
                            {
                                "item": "WSCUC Accredited",
                                "value": true
                            }
                        ]
                    },
                    {
                        "element": "Program Requirements",
                        "items": [
                            {
                                "item": "NO APPLICATION FEE",
                                "value": true
                            },
                            {
                                "item": "NO GRE",
                                "value": true
                            },
                            {
                                "item": "NO GMAT",
                                "value": true
                            }
                        ]
                    },
                    {
                        "element": "Program Length",
                        "items": [
                            {
                                "item": "1 Year Program",
                                "value": true
                            },
                            {
                                "item": "2 Year Program",
                                "value": true
                            },
                            {
                                "item": "18 Month Program",
                                "value": true
                            },
                            {
                                "item": "Accelerated",
                                "value": true
                            },
                            {
                                "item": "Advanced Standing Option",
                                "value": true
                            }
                        ]
                    }
                ],
                "location": "Location",
                "advertiserName": "Advertiser Name",
                "programName": "Program Name",
                "programDescription": "Program Description",
                "imageUrl": "https://cdn.myadoptimizer.com/maojsfiles/images/ProgramAdCopyLogo_000000_d000ac0d-a00f-000-0ba0-0a0b0yz00000.png"
}
```

Response example for campaigns with **program ad copy** not configured:
```JSON
 "programAdCopy": {
                "customVar": [
                    null,
                    null,
                    null
                ],
		"constraints": [],
                "location": "",
                "advertiserName": "",
                "programName": "",
                "programDescription": "",
		"imageUrl": ""
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
