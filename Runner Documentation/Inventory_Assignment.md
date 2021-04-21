This collection will use a CSV Template to assign multiple devices to a site.


Required Environmental Variables:

`apitoken` -  This your Mist dashboard API token.  It should have permissions to assign inventory to sites in Mist.</br>

`org_id` This is a google API token that has access to geocode APIs.


CSV Required Values:
`site_name`</br>
`mac_address`</br>
`force_reassignment` - Should be `true` or `false` - If you want to reassign inventory that is already assigned to a site, select true.  Should be all lower-case, but be warned that excel hates that (use text for cell format).



Example CSV:
```
site_name,mac_address,force_reassignment
site01,aabbccddeeff,false
```