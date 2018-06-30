# Uni Bus API Endpoints

## Required Common Parameters

There's a couple of common parameters used in the Uni Bus API which are documented below.

### HTTP Headers

The Uni Bus API's require a couple of UUID's/GUID's which must be sent along with every request. You can find more information about these UUID's in [the Uni Bus Privacy Policy](https://unibus.co/privacy.html).

* `X-UniBus-AppID` - (Required) This UUID is used to identify your application to the Uni Bus API - we'll provide you with this when you contact us and should be reused across all instances of your application.

~> **NOTE:** please [contact us](mailto:unibus@ibuildstuff.co.uk) to obtain this value.

* `X-UniBus-DeviceID` - (Required) This is a UUID/GUID which identifies this device, this value should be generated once and then stored for all requests from a given device. You can [find more information about this UUID/GUID, and what it's used for here](https://unibus.co/privacy.html).

### URI

The University Name is exposed in the URI for all resources, for instance `london`.

URI's are displayed in the documentation as `/v2/{university}/example` - which for the university `london` would be available at the endpoint `/v2/london/example`
