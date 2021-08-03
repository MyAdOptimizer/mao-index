<p align="center">
  <a href="https://myadoptimizer.com/">
    <img src="https://myadoptimizer.com/img/logo-blk.svg" alt="Logo" height="80">
  </a>
  <h3 align="center">MyAdOptimizer.com Integration Doc </h3>
  <p align="center">
    Learn how to integrate the <strong>MAO Advertiser and Data Center API</strong> by following these steps
    <br />
    <a href="https://myadoptimizer.com">View Site</a>
    ·
    <a href="https://myadoptimizer.com/contact">Report Bug</a>
  </p>
</p>

## Advertiser Report instructions

### Endpoint
<br>

```
https://api.myadoptimizer.com/api/AdRptAPI?AdToken= {{ Advertiser Token }}

// without brackets ({})
```
**You have to request your advertiser token to your PE Admin.*

### Method: POST
<br>

| Params Names        | Data Type | Allowed Values                       |
| :------------------ | :-------- | :----------------------------------- |
| Query String Params |
| AdToken             | String    | XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX |
| Post JSON Params    |
| StartDate           | Date      | yyyy-MM-dd                           |
| StartDate           | Date      | yyyy-MM-dd                           |

<br>

### Example result

```JSON
[
    {
        "campaignID": 623,
        "campaignName": "Camapign Name",
        "date": "2021-07-01T00:00:00",
        "availableImpressions": 4468,
        "impressions": 1,
        "clicks": 1,
        "cpc": 9.2800,
        "ctr": 9.2800,
        "spend": 9.800
    },
]

```
<br>

## Data center instructions

### Endpoint
<br>

```
https://api.myadoptimizer.com/api/AdRptAPI?UserToken= {{ User token provided }} dcReport=true&VerticalID= {{ Vertical ID consulted }} &StartDate= {{ yyyy-MM-dd }} &EndDate= {{ yyyy-MM-dd }}

// without brackets ({})
```

**You can find your user token in  <b> Account info </b>*

<br>

### Method: GET

<br>

| Params Names | Data Type | Allowed Values                                                                                                                     |
| :----------- | :-------- | :--------------------------------------------------------------------------------------------------------------------------------- |
| UserToken\*  | String    | XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX                                                                                               |
| dcReport\*   | Boolean   | true                                                                                                                               |
| VerticalID\* | Integer   | - 1 / Refinace <br> - 2 / Purchase <br> - 8 / Auto Insurance <br> - 11 / Education <br> - 13 / Medicare <br> - 14 / Home Insurance |
| StartDate\*  | Date      | yyyy-MM-dd                                                                                                                         |
| EndDate\*    | Date      | yyyy-MM-dd                                                                                                                         |

\*<b>Case sensitive & required values</b>

### Example result

<br>

Refinance | Purchase | Auto Insurance | Medicate | Home Insurance 

```JSON
[
    {
        "verticalName": "Refinance",
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
        "landingPageID": 00,
        "adConstraints": [
            {
                "adConstraintName": "CashOut",
                "value": "Yes"
            },

        ],
        "campaignBid": 10.0,
        "baseCPC": 9.2000,
        "baseCampaignBid": 10.0000
    },
]
```
