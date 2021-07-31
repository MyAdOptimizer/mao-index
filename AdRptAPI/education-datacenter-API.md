<p align="center">
  <a href="https://myadoptimizer.com/">
    <img src="https://myadoptimizer.com/img/logo-blk.svg" alt="Logo" height="80">
  </a>
  <h3 align="center">MyAdOptimizer.com Education Data Center API Integration Doc </h3>
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

<br>

### Method: GET

<br>

| Params Names | Data Type | Allowed Values                                                                                                                     |
| :----------- | :-------- | :--------------------------------------------------------------------------------------------------------------------------------- |
| UserToken\*  | String    | XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX                                                                                               |
| dcReport\*   | Boolean   | true                                                                                                                               |
| VerticalID\* | Integer   | 11 / Education                 |
| StartDate\*  | Date      | yyyy-MM-dd                                                                                                                         |
| EndDate\*    | Date      | yyyy-MM-dd                                                                                                                         |

\*<b>Case sensitive & obligatory values</b>

### Example result

<br>

```JSON
[
    {
        "date": "2021-07-01T23:59:58.383",
        "advertiserName": "Advertiser Name",
        "marketPlace": "Ad Network",
        "publiserID": "Publiser ID",
        "advertiserID": 430,
        "campaignName": "Campaign name",
        "adConstraints": [
            {
                "adConstraintName": "Clickout Campaign",
                "value": ""
            },
        ],
        "campaignID": 861,
        "position": 2,
        "impressions": 1,
        "clicks": 1,
        "cpc": 9.2000,
        "leads": 1,
        "extClickID": "00000000-0000-0000-0000-000000000000",
        "baseCPC": 9.2000,
        "baseCampaignBid": 10.0000
    }
]
```