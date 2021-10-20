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

<h3>Specific Query String Parameters for <strong>Education</strong></h3>

<!-- | Params Names | Data Type | Allowed Values |
| :------------------------ | :-------: | :------------- |
| ZipCode                   | string    |                |
| State*                     | string    | 2 char US code (Uppercase) |
| AdPlacement*               | string    | ICF, No Matches, After Matches, API, High School, Ad Unit, Organic Exit Pop, Paid Search Exit Pop | 
| AreaOfStudy*               | string    | Arts / Design / Fashion, Business, Communication & Multimedia, Computers & IT, Cosmetology & Beauty, Criminal Justice & Law Enforcement, Culinary Arts & Hospitality, Education & Teaching, General Studies / Undecided, Health & Medical / Nursing, Legal Professions, Massage Therapy & Healing Arts, Political Science, Psychology & Social Work, Religious Studies,Trades & Careers, Counseling, ANY |
| Concentration*             | string    | Human Services/Social Work, Medical Assistant, Medical Insurance Biller/Coder, Medical Office Assistant, Medical Transcriptionist, Nursing - Licensed Practical/Vocational Nurse Training (Certificate), Nursing - MSN, Nursing - Registered Nurse (AAS), Nursing - RN to BSN, Nursing Assistant (CNA), Personal Training / Nutrition, Pharmacy Technician/Assistant, Phlebotomy / Clinical Medical Lab. Technician, Physical Therapy & Rehabilitation, Psychology, Surgical Technologist, Ultrasound Technician, Veterinary Medicine, X-Ray/Radiologic Technician, Court Reporting, Legal Administrative Assistant, Legal Assistant/Paralegal, Legal Studies, Healing Arts & Alternative Medicine, Massage Therapy, Political Science, Business & Organizational Psychology, Clinical Psychology, Counseling Psychology, Forensic Psychology/Crime Scene Investigator, General Psychology, Human Services/Social Work, Sport Psychology, Christian Studies, Ministry, Religious Studies, Theology, Aircraft Maintenance, Auto Mechanic, Autobody Repair, Aviation, CAD Drafting and Design, Computer Installation & Repair, Computer Systems Technology, Construction Management, Electrician, Engineering Technology/Technicians, HVAC, Laboratory Technician, Plumbing Technology/Plumber, Telecommunications Technology, Truck Driving, Welding Technology/Welder, Design & Visual Communications, Fashion/Apparel Design, Film and Theater, Graphic Design, Industrial Design, Interior Design, Photography, Visual Arts, Accounting & Related Services, Administrative & Secretarial Services, Business Communications, E-Commerce/Business, Economics, Entrepreneurship & Small Business, Fashion and Apparel, Finance, General Business, Green & Sustainable Management, Hospitality & Restaurants, Human Resources, Information Systems Management, International Business, Management, Marketing, Property Management / Real Estate, Public & Non-Profit Administration, Retail & Sales, Supply Chain Management, Advertising, Animation & Video Graphics, Commercial & Advertising Art, Computer Media Applications, Design & Visual Communications, Film/Video & Cinematography, Graphic Design, Intermedia/Multimedia, Photography, Recording Arts Technology, Web Design, Computer Science, Computer Support Services, Computer Systems Security, Networking, Software Development, Systems Administration, Telecommunications, Web Design and Internet, Barbering/Barber, Cosmetology/Cosmetologist, Esthetician & Skin Care, Hair Styling & Hair Design, Make-Up Artist/Specialist, Manicurist/Nail Specialist, Correctional Officer (Prison Officer), Criminal Justice & Law Enforcement/Police, Fire Science, Forensics/Crime Scene Investigation, Homeland Security, Security Services, Baking and Pastry Arts, Culinary Arts, Food Services, Hospitality Management, Restaurant & Food Services, Tourism & Travel Management, Administration & Leadership, Curriculum and Instruction, Early Childhood Education, Education and Teaching, General Education, Secondary Education, General Studies, Liberal Arts, Undecided, Alternative Medicine/Healing Arts, Dental Assisting, Dental Hygienist, Diagnostic & Treatment Technician, Gerontology, Health Information Technology/Records, Healthcare Administration, Business Administration,
Business Intelligence, Organizational Leadership, Project Management, Taxation, Analytics & Data Science, Engineering, Information & Library Sciences, Information Technology/Systems, Addictions & Recovery, Counseling,Family Counseling, Mental Health Counseling, School Counseling, Criminal Justice, Criminology, Educational Technology, Elementary Education, Music Education, Reading & Literacy, Special Education, Teaching, Emergency Management, Nurse Education, Nurse Practitioner (RN Required), Public Health, Speech Pathology/Therapy, Behavioral Psychology, Child Psychology, Educational Psychology, ANY |
| DegreeLevel*               | string    | CERTIFICATE, ASSOCIATES, BACHELORS, MASTERS, DOCTORATE |
| HighSchoolGradYear        | Integer   | 2020, 2019, 2018, 2017, 2016, 2015, 2014, 2013, 2012, 2011, 2010, 2009, 2008, 2007, 2006, 2005, 2004, 2003, 2002, 2001, 1990 |
| HighestEducationLevel*     | string    | STILL_IN_HIGH_SCHOOL, NO_HIGH_SCHOOL_OR_GED, HIGH_SCHOOL, SOME_COLLEGE, ASSOCIATES_DEGREE, BACHELORS_DEGREE, MASTERS_DEGREE, DOCTORAL_DEGREE, GED |
| LearningPreference*        | string    | CAMPUS, ONLINE, HYBRID, ANY |
| LikelihoodToEnroll*        | string    | NOT_LIKELY, SOMEWHAT_LIKELY, VERY_LIKELY |
| MilitaryStatus*            | string    | true, false, null |
| RNDegree*                  | string    | true, false, null |
| StartDate*                 | string    | LESS_THAN_1_MONTH, 1_TO_3_MONTHS, 3_TO_6_MONTHS, 6_TO_12_MONTHS, OVER_12_MONTHS |
| USCitizen *                | string    | true, false, null |
| Accreditations*             | string    | Regionally Accredited, Nationally Accredited, Cacrep Accredited, Mpcac Accredited | 
| Program Length*             | string    | 1 Year Program, 2 Year Program, 18 Month Program, Accelerated, Advanced Standig Option | 
| Requirements*              | string    | No GRE, No GMAT |
| FName ±                    | string    |  |
| LName ±                   | string    |  |
| Email ±                    | string    |  |
| Phone ±                    | string    |  |
| Address ±                  | string    |  |
| City ±                     | string    |  | -->

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
        <td colspan=2 >ICF, No Matches, After Matches, API, High School, Ad Unit, Organic Exit Pop, Paid Search Exit Pop</td>
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
        <td colspan=2>CAMPUS, ONLINE, HYBRID, ANY</td>
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
        <td>Accreditations*</td>
        <td>string</td>
        <td colspan=2>Regionally Accredited, Nationally Accredited, Cacrep Accredited, Mpcac Accredited</td>
    </tr>
    <tr>
        <td>ProgramLength*</td>
        <td>string</td>
        <td colspan=2>1 Year Program, 2 Year Program, 18 Month Program, Accelerated, Advanced Standig Option</td>
    </tr>
    <tr>
        <td>Requirements*</td>
        <td>string</td>
        <td colspan=2>No GRE, No GMAT</td>
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

±PII Fields

## LocalStorage Integration

If you want to use LocalStorage instead Querystring. Set up the parameters values stated above. MyAdOptimizer provide you a method called **setMAOLocalStorageValue** for do it.

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
initMAO('target', 1);
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
