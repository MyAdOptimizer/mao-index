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

## Description

API to turn on or off a campaign.

### EndPoint

```
https://api.myadoptimizer.com/api/AdCampaignAPI?AdToken= {{ Token provided }} &CampaignID = {{ Campaign ID }} &ActivateCampaign = {{ 0 => false | 1 => true }}

// without brackets ({})
```

\*\* AdToken will be provided by your account manager.

### Method: GET

It requires 3 parameters

<table>
    <thead>
        <tr>
            <th>Params Names</th>
            <th>Data Tpye</th>
            <th>Allowed Values</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td> AdToken </td>
            <td> String </td>
            <td> XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX </td>
        </tr>
        <tr>
            <td> CampaignID </td>
            <td> Integer </td>
            <td>  0-2,147,483,647</td>
        </tr>
        <tr>
            <td> ActivateCampaign </td>
            <td> Integer </td>
            <td> (Pass 0 to turn it off. Pass 1 to turn it on)  </td>
        </tr>
    </tbody>
</table>

## Example 1 | Turn off Campaign

### API Call

```
 https://api.myadoptimizer.com/api/AdCampaignAPI?AdToken=63fb22bf-25da-4ea2-a79b-4838374b2d99&CampaignID=10&ActivateCampaign=0

```

### Result

```JSON
{
	"token": "63fb22bf-25da-4ea2-a79b-4838374b2d99",
	"ipAddress": "100.189.154.210",
	"activateCampaign": false,
	"campaignID": 10,
	"eventID": "891c85d0-5bd9-4635-8c8d-b703615006d2"
}
```

## Example 2 | Turn on Campaign

### API Call

```
https://api.myadoptimizer.com/api/AdCampaignAPI?AdToken=63fb22bf-25da-4ea2-a79b-4838374b2d99&CampaignID=10&ActivateCampaign=1

```

### Result

```JSON
{
	"token": "63fb22bf-25da-4ea2-a79b-4838374b2d99",
	"ipAddress": "100.189.154.210",
	"activateCampaign": true,
	"campaignID": 10,
	"eventID": "332bfce5-0932-478b-b4a9-ba3c8fd800d9"
}
```

\*\* token: is the advertiser token a given campaign belongs to
