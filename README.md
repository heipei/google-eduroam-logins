Google Eduroam Logins
=====================

Author: Johannes Gilger <heipei@hackvalue.de>

Description
-----------

This is a simple project meant to extract logins from radsecproxy-logs in order
to display login-counts from different institutions on a map.

Installation
------------

In order to use this you'll need the following:
- ruby installed
- geoip ruby gem installed
- geopiplookup libraries installed system-wide (optional)
- a valid Google Maps API key

Usage
-----

Start by downloading an up-to-date version of GeoLiteCity.dat (using the
update\_db.sh script). Or use the commercial version if you've got that ;)

generate.sh then gets the relevant information from the MySQL server (make sure
that .passwd with your SQL-pw exists) and returns it in two columns:
<usercount> <domain>

The institutions.rb script tries to resolve the domain and then looks up the IP
using the GeoIP libs. It directly returns snippets of JavaScript-code which are
included in the html and used to fill out the corresponding divs.


Development
-----------

Outstanding bugs and problems are documented in the TODO. Patches to general
problems (i.e. not special to your local setup) are gladly accepted at
heipei@hackvalue.de. If possible use git to manage the source and generate
commits as patches (see git format-patch).

License
-------

Licensed as Open Source under the GPLv2. Have fun ;)
