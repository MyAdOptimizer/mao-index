<p align="center">
  <a href="https://myadoptimizer.com/">
    <img src="https://myadoptimizer.com/img/logo-blk.svg" alt="Logo" height="80">
  </a>
  <h3 align="center">MyAdOptimizer.com Data Center API Integration Doc </h3>
  <p align="center">
    Learn how to integrate the <strong>MAO Data Center API</strong> by following these steps
    <br />
    <a href="https://myadoptimizer.com">View Site</a>
    ·
    <a href="https://myadoptimizer.com/contact">Report Bug</a>
  </p>
</p>

### Endpoint
<br>

```
https://api.myadoptimizer.com/api/AdRptAPI?UserToken= {{ User token provided }} dcReport=true&VerticalID= {{ Vertical ID consulted }} &StartDate= {{ yyyy-MM-dd }} &EndDate= {{ yyyy-MM-dd }}

// without brackets ({})
```

**You can find your user token in  <b> Account info </b>*

![Item](https://github.com/MyAdOptimizer/mao-index/assets/86742967/dbdaefed-dc03-4311-8106-ae30c9dbbe13)

<br>

### Method: GET

<br>

| Params Names | Data Type | Allowed Values                                                                                                                     |
| :----------- | :-------- | :--------------------------------------------------------------------------------------------------------------------------------- |
| UserToken\*  | String    | XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX                                                                                               |
| dcReport\*   | Boolean   | true                                                                                                                               |
| VerticalID\* | Integer   | - 1 / Refinace <br> - 2 / Purchase <br> - 8 / Auto Insurance <br> - 9 / Life Insurance <br> - 13 / Medicare <br> - 14 / Home Insurance <br> - 15 / Solar <br> - 16 / Personal Loans <br> - 17 / Home Services <br> |
| StartDate\*  | Date      | yyyy-MM-dd                                                                                                                         |
| EndDate\*    | Date      | yyyy-MM-dd | 
| Clicks       | INT       | 1 (Clicks Only) 0 (Clicks & Impressions) |

\*<b>Case sensitive & required values</b>

### Example result

<br>

Refinance | Purchase | Auto Insurance | Medicate | Home Insurance example result

```JSON
[
    {
        "verticalName": "Vertical Name",
        "landingPage": "Name of landing page",
        "adNetowrk": "Ad Network",
        "campaignID": 685,
        "campaignName": "Campaign Name",
        "advertiserID": 537,
        "advertiserName": "Advertiser Name",
        "eventID": "00000000-0000-0000-0000-000000000000",
        "timeStamp": "2021-07-01T23:59:10.89",
        "cpc": 9.2000,
        "sourceID": "Source ID",
        "landingPageID": 0,
        "adConstraints": [
            {
                "adConstraintName": "CashOut",
                "value": "Yes"
            },

        ],
        "campaignBid": 10.0,
        "baseCPC": 9.2000,
        "baseCampaignBid": 10.0000,
        "brandName": "Brand Name",
        "extClickID": "00000000-0000-0000-0000-000000000000",
        "adCopyVersion": 1,
        "customVar1": "CustomVar1",
        "customVar2": "",
        "customVar3": "",
        "customVar4": "",
        "customVar5": ""
    },
]
```
Personal Loans
```JSON
[
    {
        "timeStamp": "2024-05-01T23:49:49.707",
        "landingPage": "Landing page name",
        "sourceID": "Source ID",
        "adNetwork": "AdNetwork Name",
        "advertiserID": 123,
        "advertiserName": "Advertiser Name",
        "campaignID": 123,
        "campaignName": "Campaign Name",
        "adConstraints": [
            {
                "adConstraintName": "Age",
                "value": ""
            },
            {
                "adConstraintName": "BorrowAmount",
                "value": ""
            },
        ],
        "position": 1,
        "impressions": 1,
        "clicks": 1,
        "cpc": 1.0000,
        "campaignBid": 1.0000,
        "leads": 0,
        "extClickID": "",
        "baseCPC": 0.0,
        "baseCampaignBid": 1.0000,
        "brandName": "Brand name",
        "adCopyVersion": 1,
        "customVar1": "",
        "customVar2": "",
        "customVar3": "",
        "customVar4": "",
        "customVar5": "",
        "advertiserTag": ""
    },
]
```

