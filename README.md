# ![LOGO](logo.png) HERE Tracking **flow**ground Connector

## Description

A generated **flow**ground connector for the HERE Tracking API (version 2.0.0).

Generated from: https://api.apis.guru/v2/specs/here.com/tracking/2.0.0/swagger.json<br/>
Generated at: 2019-05-07T17:42:17+03:00

## API Description

HERE Tracking is a cloud product designed to address location tracking problems for a wide range of Location IoT industry verticals.

HERE Tracking exposes a set of REST APIs and client libraries to enable location tracking and geo-fencing for a variety of device form-factors including small-footprint (small memory and processing power) devices. HERE Tracking also includes end-user applications on mobile and web to be used as reference apps to demonstrate the product capabilities.

## Authorization

Supported authorization schemes:
- API Key- API Key- API Key
## Actions

### Gets service health

*Tags:* `Device Associations`

### Gets service version

*Tags:* `Device Associations`

### Retrieves geofences associated with the device

> Returns all fences tracking id has been associated with

*Tags:* `Device Associations`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `trackingId` - _required_ - The ID HERE Tracking assigned to the device when it was claimed by a user.
* `pageToken` - _optional_ - A page token that you can use to retrieve the next page.
* `count` - _optional_ - The number of items to return per page.

### Gets service health

*Tags:* `Geofence association`

### Gets service version

*Tags:* `Geofence association`

### Gets devices associated with this geofence

> This returns a list of devices that are associated with this geofence.<br/>
> <br/>
> Note: A device appearing in this list does not mean the device is inside the geofence.

*Tags:* `Geofence association`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `geofenceId` - _required_ - Geofence ID
* `pageToken` - _optional_ - A page token that you can use to retrieve the next page.
* `count` - _optional_ - The number of items to return per page.

### Disassociates a device and a geofence

> Notification will no longer be generated when the device enters or exits this geofence.

*Tags:* `Geofence association`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `geofenceId` - _required_ - Geofence ID
* `trackingId` - _required_ - The ID HERE Tracking assigned to the device when it was claimed by a user.

### Associates a device with a geofence

> Notifications will be generated when the device enters or exits this geofence

*Tags:* `Geofence association`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `geofenceId` - _required_ - Geofence ID
* `trackingId` - _required_ - The ID HERE Tracking assigned to the device when it was claimed by a user.

### Deletes all geofences

> Deletes all geofences created by the provided user account.<br/>
> <br/>
> As an extra safety measure, you must also supply the header `x-confirm`<br/>
> with the value `true`. If this header is not explicitly specified on a<br/>
> **Delete All** request, the request fails.

*Tags:* `Geofences`

#### Input Parameters
* `x-confirm` - _required_ - A safety measure that prevents you from accidentally deleting data.

To confirm that all entries should be deleted, set the value to "true".

    Possible values: true.

### Gets all geofences

> Provides all geofence definitions in a paginated JSON oject.

*Tags:* `Geofences`

#### Input Parameters
* `pageToken` - _optional_ - A page token that you can use to retrieve the next page.
* `count` - _optional_ - The number of items to return per page.

### Creates a geofence

> You can specify a geofence as a circle or as a polygon. You can also assign<br/>
> a name and a description to each geofence to help identify them. If no name<br/>
> is assigned, the geofence is named using a unique ID.<br/>
> <br/>
> Circle<br/>
> ---<br/>
> <br/>
> Specify the coordinates of the center point of the circle and a radius in<br/>
> meters.<br/>
> <br/>
> ```json<br/>
>     {<br/>
>         "name": "Home"<br/>
>         "definition": {<br/>
>             "center": {<br/>
>                 "lat": 52.5308398,<br/>
>                 "lng": 13.38490035<br/>
>             },<br/>
>             "radius": 100<br/>
>         },<br/>
>         "description": "Small area around my house."<br/>
>     }<br/>
> ```<br/>
> <br/>
> Polygon<br/>
> ---<br/>
> <br/>
> Specify an array of points. A minimum of three points are required.<br/>
> <br/>
> *NOTE: If the points do not describe a closed polygon, the polygon is<br/>
> automatically closed between the last and first points.*<br/>
> <br/>
> ```json<br/>
>     {<br/>
>         "name": "Work"<br/>
>         "definition": {<br/>
>             "points": [{<br/>
>                 "lat": 52.5308398,<br/>
>                 "lng": 13.38490035<br/>
>             }, {<br/>
>                 "lat": 52.530443,<br/>
>                 "lng": 13.38482003<br/>
>             }, {<br/>
>                 "lat": 52.5308298,<br/>
>                 "lng": 13.38492235<br/>
>             }]<br/>
>         },<br/>
>         "description": "The area around work."<br/>
>     }<br/>
> ```<br/>
> <br/>
> Successful requests have the HTTP status 201 and the response body provides<br/>
> the ID of the created geofence.

*Tags:* `Geofences`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.


### Gets service health

*Tags:* `Geofences`

### Gets service version

*Tags:* `Geofences`

### Deletes a geofence

> Deletes a single geofence definition based on the provided geofence ID.

*Tags:* `Geofences`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `geofenceId` - _required_ - ID of the geofence

### Gets a single geofence

> Provides the details of a single geofence definition such as the shape,<br/>
> name and description.

*Tags:* `Geofences`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `geofenceId` - _required_ - ID of the geofence

### Updates a single geofence

> Update the geofence shape, name or description. After a successful update,<br/>
> the response provides updated geofence details.

*Tags:* `Geofences`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `geofenceId` - _required_ - ID of the geofence

### Gets service health

*Tags:* `Notifications`

### Registers for notifications

> Registers users for notifications when a device transitions into or out of<br/>
> a geofence.<br/>
> <br/>
> The input data can be only the following:<br/>
>  * A URL to receive webhook notifications

*Tags:* `Notifications`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.


### Unregisters from notifications

> Unregister from notifications for the specified channel.<br/>
> <br/>
> The only channel name currently supported is 'webhook' for webhook notifications

*Tags:* `Notifications`

#### Input Parameters
* `channelName` - _required_ - The name of the notification channel from which to unregister.


### Gets all registered notification channels

> Gets a list of all previously registered notification channels.<br/>
> <br/>
> The responded channel name(s) will be 'webhook' if a webhook URL has been registered

*Tags:* `Notifications`

### Gets service version

*Tags:* `Notifications`

### Gets the trackingId for a device

> When provided with a deviceId, this endpoint returns the tracking ID for a previously claimed device.

*Tags:* `Registry`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `deviceId` - _required_ - The device ID provided when provisioning a device

### Claims a device

> Claim a device to a user. Before a device is claimed, it cannot complete<br/>
> login and any data sent to the ingestion endpoint will be ignored. Once a<br/>
> device is claimed, its data is stored and available to its owner.<br/>
> <br/>
> When a device is claimed, it will be assigned a trackingID. This is the<br/>
> identifier in HERE Tracking that the data is associated with. Having a<br/>
> separate deviceId and trackingId means that devices can have their ownership<br/>
> transferred without having to create and install a new deviceId and<br/>
> deviceSecret.

*Tags:* `Registry`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `deviceId` - _required_ - The device ID provided when provisioning a device

### Gets service health

*Tags:* `Registry`

### Gets service version

*Tags:* `Registry`

### Creates credentials for multiple devices

> Starts a batch job to create credentials for the number of devices specified in the body.

*Tags:* `Registry`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `appId` - _required_

### get count of created licenses for a given vendor's app id

> Retrieves the count of already created licenses

*Tags:* `Registry`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `appId` - _required_

### Creates credentials for a single device

> The credentials will be created. The ID and secret will instantly be returned in the body.<br/>
> <br/>
> If autoclaim=true, the created device is immediately bound to the requesting account.

*Tags:* `Registry`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `appId` - _required_
* `autoclaim` - _optional_ - If set to `true`, the license is created and immediately claimed by the same user.

### Gets the job results

> This returns the results of the given batch job if the job has completed.

*Tags:* `Registry`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `jobId` - _required_ - UUID v.4.0
* `pageToken` - _optional_ - A page token that you can use to retrieve the next page.
* `count` - _optional_ - The number of items to return per page.

### Gets the job status

> Use this endpoint to check the progress of a previously created<br/>
> credentials request.

*Tags:* `Registry`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `jobId` - _required_ - UUID v.4.0

### Unclaims a device

> Removes the association between the user and the device. The device is no longer able to generate data for the user and can now be registered by another user (or the same user again).

*Tags:* `Registry`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `trackingId` - _required_ - The ID HERE Tracking assigned to the device when it was claimed by a user.

### Gets the deviceId

> When provided with a trackingId, this endpoint returns the deviceId for a previously claimed device.

*Tags:* `Registry`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `trackingId` - _required_ - The ID HERE Tracking assigned to the device when it was claimed by a user.

### Gets a batch of device shadows

> Provides shadow objects for multiple devices. You can get shadows for a<br/>
> maximum of 20 devices per request.

*Tags:* `Shadows`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.


### Gets service health

*Tags:* `Shadows`

### Gets service version

*Tags:* `Shadows`

### Clears the device shadow

> Deletes the information inside a device's shadow object. The shadow object<br/>
> itself is retained, but all values for `desired` and `reported`<br/>
> properties are cleared.

*Tags:* `Shadows`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `trackingId` - _required_ - The ID HERE Tracking assigned to the device when it was claimed by a user.

### Gets the device shadow

> Provides a shadow object that contains `reported` and `desired` properties<br/>
> for a device configuration. When setting the header parameters, make sure<br/>
> that you provide a HERE Account token that allows read access.

*Tags:* `Shadows`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `trackingId` - _required_ - The ID HERE Tracking assigned to the device when it was claimed by a user.

### Updates the device shadow

> Updates the device shadow that is stored in HERE Tracking.<br/>
> <br/>
> The device shadow contains 'reported' and 'desired' configuration states<br/>
> for a device.<br/>
> <br/>
> Request<br/>
> ---<br/>
> <br/>
> The body is a shadow object with either an update to the `desired` or<br/>
> `reported` configuration state.<br/>
> <br/>
> You cannot use the same request to update the `desired` and `reported`<br/>
> properties simultaneously. Instead, use separate requests for each type of<br/>
> configuration state.<br/>
> <br/>
> Response<br/>
> ---<br/>
> <br/>
> The response body is a shadow object that shows the difference between the<br/>
> `reported` and the `desired` states. It contains properties that don't<br/>
> match across the two configurations.<br/>
> <br/>
> The response example shows the response to the previous request example<br/>
> where the `desired` state was updated.<br/>
> <br/>
> If all `reported` and `desired` properties match, the response object<br/>
> contains only the trackingId and timestamp properties.

*Tags:* `Shadows`

#### Input Parameters
* `content-length` - _required_ - The size of the shadow in bytes. The size is validated against the maximum
limit of 1000 bytes.

* `trackingId` - _required_ - The ID HERE Tracking assigned to the device when it was claimed by a user.

### Gets the value for a property

> Gets the value for the requested state. You can use request either <br/>
> `desired` or `reported` device state.

*Tags:* `Shadows`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `trackingId` - _required_ - The ID HERE Tracking assigned to the device when it was claimed by a user.
* `state` - _required_ - Desired or reported state to query.
    Possible values: desired, reported.

### Gets the value for a property

> Gets the value for a single property in the given state. You can use<br/>
> JSON selectors to select values for `desired` or `reported` properties.<br/>
> You can also reference a property by name, but if the property contains<br/>
> an object, the entire object is returned rather than a distinct value.<br/>
> <br/>
> The JSON selector can be nested like this: `payload/time/minutes`

*Tags:* `Shadows`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `trackingId` - _required_ - The ID HERE Tracking assigned to the device when it was claimed by a user.
* `state` - _required_ - Desired or reported state to query.
    Possible values: desired, reported.
* `selector` - _required_ - A JSON selector that specifies the property to get information.
If not supplied, the entire state is returned.


### Gets service health

*Tags:* `Traces`

### Gets service version

*Tags:* `Traces`

### Deletes the entire history of the device

> Deletes all historical data for a device including **traces** and **transitions**.

*Tags:* `Traces`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `trackingId` - _required_ - The ID HERE Tracking assigned to the device when it was claimed by a user.

### Gets the trace within a specified time range

> Gets all traces that were recorded within the specified time range.<br/>
> <br/>
> Define the range with "before" and "after" timestamps. A successful<br/>
> response contains an array of traces that were recorded after the<br/>
> first timestamp and before the second.<br/>
> <br/>
> Traces are returned as an array in descending order based on timestamp.<br/>
> <br/>
> Note:<br/>
> ---<br/>
> <br/>
> To ensure a fast response, always provide both `before` and `after` timestamps.<br/>
> <br/>
> If no values are supplied `after` defaults to 0, and `before` defaults<br/>
> to the current system time.<br/>
> <br/>
> The `count` and `pageToken` parameters provide pagination for results<br/>
> where a large volume of data matches the given time range.<br/>
> <br/>
> <br/>
> In this case, `count` is the number of records returned per page along with<br/>
> a `pageToken` header in the returned HTTP response. The `pageToken` indicates<br/>
> the next available page in the matching result set. To get the next page of<br/>
> records, submit `pageToken` as a query parameter in your next request. The default<br/>
> number of records per page is 1000, which is also the maximum number of<br/>
> records per page.<br/>
> <br/>
> In case of success, the response body contains an array of trace<br/>
> samples between the given timestamps (after <= timestamp <= before).

*Tags:* `Traces`

#### Input Parameters
* `before` - _optional_ - Milliseconds elapsed since 1 January 1970 00:00:00 UTC.
The accepted range is from 1 to the current time.

* `after` - _optional_ - Milliseconds elapsed since 1 January 1970 00:00:00 UTC.
The accepted range is from 0 to the current time.

* `pageToken` - _optional_ - A page token that you can use to retrieve the next page.
* `count` - _optional_ - The number of records per page.
* `filter` - _optional_ - If you set this to "true", the trace sample is passed through a Kalman smoothing filter.
The default is `false`.


### Gets transitions for a device

> Gets all transitions that were recorded within a specific time range. This<br/>
> log also includes events when the accuracy radius of the reported position<br/>
> intersects with a geofence boundary.<br/>
> <br/>
> You define the range with `before` and `after` timestamps. A successful<br/>
> response contains an array of transitions that were recorded after the<br/>
> first timestamp and before the second.<br/>
> <br/>
> Transitions are listed in descending order based on the timestamp.<br/>
> <br/>
> Note:<br/>
> ---<br/>
> <br/>
> To ensure a fast response, always provide both `before` and `after` timestamps.<br/>
> <br/>
> If no values are supplied `after` defaults to 0, and `before` defaults<br/>
> to the current system time.<br/>
> <br/>
> The `count` and `pageToken` parameters provide pagination for results<br/>
> where a large volume of data matches the given time range.<br/>
> <br/>
> In this case, `count` is the number of records returned per page along with<br/>
> a `pageToken` header in the returned HTTP response. The `pageToken` indicates<br/>
> the next available page in the matching result set. To get the next page of<br/>
> records, submit `pageToken` as a query parameter in your next request. The default<br/>
> number of records per page is 1000, which is also the maximum number of<br/>
> records per page.

*Tags:* `Transitions`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `trackingId` - _required_ - The ID HERE Tracking assigned to the device when it was claimed by a user.
* `before` - _optional_ - Milliseconds elapsed since 1 January 1970 00:00:00 UTC.
The accepted range is from 1 to the current time.

* `after` - _optional_ - Milliseconds elapsed since 1 January 1970 00:00:00 UTC.
The accepted range is from 0 to the current time.

* `pageToken` - _optional_ - A page token that you can use to retrieve the next page.
* `count` - _optional_ - The number of items to return per page.

### Gets service health

*Tags:* `Transitions`

### Gets service version

*Tags:* `Transitions`

### Gets all devices owned by a given user

> Provides an array of the TrackingIds for devices that the given user owns.

*Tags:* `Users`

#### Input Parameters
* `pageToken` - _optional_ - A page token that you can use to retrieve the next page.
* `count` - _optional_ - The number of items to return per page.

### Gets service health

*Tags:* `Users`

### Gets a valid access token

> Use this to get a valid access token for a given HERE Account email and password.

*Tags:* `Users`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.


### Gets a valid access token given a refreshToken

> Use this to get a valid access token for a given HERE Account access token and refresh token.

*Tags:* `Users`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.


### Gets service version

*Tags:* `Users`

### Sends data and receives shadow

> A device uses its access token to send data to HERE Tracking.<br/>
> <br/>
> If the request is set to be synchronous, the response will be<br/>
> the desired state of the device shadow. If the request is set<br/>
> to be asynchronous, the response will be empty.<br/>
> <br/>
> To have a position associated with a device, the request body must contain<br/>
> either a `position` or a `scan` object (see the object definitions for<br/>
> details). If both are provided, the `scan` is resolved to a `position`. The<br/>
> more accurate of the two positions (provided and resolved) is used as the<br/>
> device's position.<br/>
> <br/>
> If a `scan` is provided, HERE Tracking will resolve the position asynchronously<br/>
> and return the desired state. The shadow will then be updated<br/>
> immediately after responding.

*Tags:* `Ingestion`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `authorization` - _required_
* `async` - _optional_ - If set to true, sends the device's data and responds immediately with an empty response body.

### Gets service health

*Tags:* `Ingestion`

### Gets the current timestamp

> Returns the server timestamp used to check the validity of a device's OAuth 1.0 header. Devices must synchronise with this timestamp to avoid clock skew.

*Tags:* `Ingestion`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.


### Requests a token for a registered device

> HERE Tracking requires that you sign your requests for tokens.<br/>
> The signature method uses the OAuth 1.0 standard. For more<br/>
> information on this standard, see the [OAuth Core<br/>
> 1.0](https://oauth.net/core/1.0/) specification.<br/>
> <br/>
> > See the Authentication section for details on how to generate a signed token request.

*Tags:* `Ingestion`

#### Input Parameters
* `x-request-id` - _optional_ - ID used for correlating requests within HERE Tracking. Used for logging and error reporting.

Must be a valid UUIDv4.

* `authorization` - _required_ - Signed OAuth 1.0 header

### Gets service version

*Tags:* `Ingestion`

## License

**flow**ground :- Telekom iPaaS / here-com-tracking-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
