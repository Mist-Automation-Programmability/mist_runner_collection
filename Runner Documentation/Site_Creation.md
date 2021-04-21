This collection will use a CSV Template to create multiple sites via the Mist API.

It also uses a google API to get the lat/long of the address and use the properly formatted address returned from Google Maps.

## Required Environmental Variables:

`apitoken` -  This your Mist dashboard API token.  It should have permissions to create sites in Mist. </br></br>

## Optional Environment Variables
`google_api_token` This is a google API token that has access to geocode APIs.  If you provide all the geocoding/timezone values, this will not be required.  See Scenario `Skip Geocoding`


## CSV Required Values:
`site_name`</br>
`site_address` This address should be in quotes in the CSV if it contains commas. </br>

## CSV Optional Values:
`sitegroup_ids` this should be presented as a JSON list of sitegroup IDs.
* Example: `["xxxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"]`</br></br>

`rftemplate_id` This should be the rftemplate_id you want applied to this site
* Example: `xxxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx` </br>

`alarmtemplate_id` This should be the alarmtemplate_id you want applied
* Example: `xxxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx` </br>

## Scenario Options:

### Skip Geocoding:
In order to skip geocoding, you must provide the following values in the CSV.  See the example CSV for details on what these should look like

#### Required Values:
* `lat` this is the site lattitude
* `lng` this is the site longitude
* `time_zone` This is the site time_zone
* `country_code`: The 2 letter country code.

### Clone Existing Site
In this scenario, we are going to clone the settings of an existing site, and create a new site with the values passed in.

#### Required Values:
* `site_template_name` This is the name of the site you want to copy.


## Example CSV:

```
site_name,site_address,rftemplate_id,lat,lng,time_zone,country_code,site_template_name,sitegroup_ids,alarmtemplate_id
SkipGeocoding-Site,"700 W Jefferson St, Boise, ID 83702",,43.6178216,-116.1995185,America/Boise,US,,,
Cloning-Site,"350 State St, Salt Lake City, UT 84103",,,,,,Jake R Snyder,,
NormalCreation-Site,"900 Court St NE, Salem, OR 97301",,,,,,,,
SkipGeocoding-Site,"700 W Jefferson St, Boise, ID 83702",,43.6178216,-116.1995185,America/Boise,US,,,
NormalCreation-Site,"900 Court St NE, Salem, OR 97301",,,,,,,,
Washington4,"416 Sid Snyder Avenue SW, Olympia, Washington 98504",,,,,,,,
''000001'',1497 Route 206 Tabernacle NJ 08088,,,,,,,,
''000001'',1497 Route 206 Tabernacle NJ 08088,,,,,,,,
Normal Site with RF Template,"900 Court St NE, Salem, OR 97301",9f65efea-0535-43af-80e5-f9f7d2bb8917,,,,,,,
Normal Site with SiteGroup,"900 Court St NE, Salem, OR 97301",,,,,,,"[""31d37657-64c7-4e7d-98d2-1b077160b952""]",
Normal Site with AlarmTemplate,"900 Court St NE, Salem, OR 97301",,,,,,,,4c4e03b2-5774-430f-8c57-6fbd1251f3df
```
