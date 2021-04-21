This collection will iterate through sites and set the payload to the settings you define in the `updateSiteSettings - Firmware` API call

You can source the data from a CSV with `site_name`, or you can run the `getSites - Send and Download` to generate a json payload with all sites.

Required Environmental Variables:
`apitoken` This your Mist dashboard API token.  It should have permissions to modify sites

## Required:

Edit the payload of `updateSiteSettings - Firmware` to specify the firmware settings you want.