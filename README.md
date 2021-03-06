<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [1. Fleettrack API documentation](#1-fleettrack-api-documentation)
  - [1.1 Efleet Documentation](#11-efleet-documentation)
    - [1.1.1 Create geofence](#111-create-geofence)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# 1. Fleettrack API documentation

All apis calls to fleettrack server should be addressed to `https//app.fleettrack.co.in`

## 1.1 Efleet Documentation
### 1.1.1 Create geofence
This api is called by `efleet` to create a geofence with `loadId`, `loadType` and `clientCode`

Method | Endpoint | Parameters | Explanation
-- | -- | -- | --
GET | `/api/efleet/create_geofence_with_loadid` | token | **Token to authenticate efleet to fleettrack api service. This is constant for efleet.
  |   | clientCode | **Identify the client
  |   | loadId | **Id unique to each geofence point
  |   | loadType | **Loading/Unloading type [L/UL]

  
**Success Response**<br/>
 Redirect to `https://efa.fleettrack.co.in`

**Failure Response**
<br/>
`res.data` contains the follwoing payload.
```
{
    response: -1,
    message: <Error message appears here>
}
```

**Example**

`https://app.fleettrack.co.in/api/efleet/create_geofence_with_loadid?token=mocl_dummy_token&clientCode=mocl&loadId=test&loadType=L`

After creating geofence the url will redirect to [efa.fleettrack.co.in](efa.fleettrack.co.in) where you should enter the `username` and `password` for the **client** for which you are creating the geofence.
