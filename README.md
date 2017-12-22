GeoServer minimal "data dir"
============================

This directory provides an empty GeoServer data directory, as such this directory does not contain any published data and is not subject to a data license.

It is highly recommended to use this minimal data dir rather than letting geoserver create his own (see why in [issue 600](https://github.com/georchestra/georchestra/issues/600))

Use the branch matching your geOrchestra version !

This repository holds 4 branches:
 - ```master``` contains geoserver minimal data dir, with a very light geOrchestra flavor:
   - [REST security](http://docs.geoserver.org/stable/en/user/security/rest.html) configuration is updated so that members with the ```GN_*``` or ```USER``` LDAP roles have read access while members of the ```ADMINISTRATOR``` group have write access,
   - [Control Flow extension](http://docs.geoserver.org/stable/en/user/extensions/controlflow/index.html) basic configuration is done,
   - the [monitoring extension](http://docs.geoserver.org/stable/en/user/extensions/monitoring/index.html) is configured with the 'live' profile,
   - the integrated GeoWebCache has [directWMSIntegration](http://docs.geoserver.org/stable/en/user/geowebcache/using.html#direct-integration-with-geoserver-wms) enabled,
   - the EPSG:27572 srs has been overridden in order to fix a ~350m shift, see [https://github.com/georchestra/georchestra/issues/379](https://github.com/georchestra/georchestra/issues/379)
 - ```geofence``` is the same as master, but:
   - ```GeofenceAuthenticationProvider``` replaces GeoServer's own ```UsernamePasswordAuthenticationProvider``` class.
   - "Production logging" quiets GeoFence logging
