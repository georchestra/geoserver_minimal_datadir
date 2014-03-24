GeoServer minimal datadir
=========================

This directory provides an empty GeoServer data directory, as such this directory does not contain any published data and is not subject to a data license.

It is highly recommended to use this minimal data dir rather than letting geoserver create his own (see why in https://github.com/georchestra/georchestra/issues/600)

This repository holds two branches:
 - ```master``` contains geoserver's minimal data dir, with a very light geOrchestra flavor:
   - [REST security](http://docs.geoserver.org/2.3.2/user/security/rest.html) configuration is updated so that members of ```SV_*``` LDAP groups have read access while members of ```SV_ADMINISTRATOR``` have write access,
   - [Control Flow extension](http://docs.geoserver.org/2.3.2/user/extensions/controlflow/index.html) basic configuration is done,
   - the [monitoring extension](http://docs.geoserver.org/2.3.2/user/extensions/monitoring/index.html) is configured with the 'live' profile,
   - the integrated GeoWebCache has [directWMSIntegration](http://docs.geoserver.org/2.3.2/user/geowebcache/using.html#direct-integration-with-geoserver-wms) enabled.
 - ```geofence``` is the same as master, but ```GeofenceAuthenticationProvider``` replaces GeoServer's own ```UsernamePasswordAuthenticationProvider``` class.
