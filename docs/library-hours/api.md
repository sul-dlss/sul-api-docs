---
id: api
title: Library Hours
---
Library Hours is an application that allows Stanford Libraries to set hours of operation for various libraries on campus. It also provides an API in which consumers can query information about the hours of operations.


## API

The base url used for this service is `https://library-hours.stanford.edu`. The Hours API uses the [JSON:API specification](https://jsonapi.org/).

### Summary

```
GET /libraries/{library_id}/locations/{location_id}.json?from={start_date}&to={end_date}
```

### Parameters
Name | Located In | Description | Required | Type | Default | Example
---- | ---------- | ----------- | -------- | ------ | ------- | ------
`library_id` | url | ID of a library | Yes | string | null | `green`
`location_id` | url | ID of a location within a library | Yes | string | null | `information-center`
`start_date` | params | Date range start for requesting location hours. Accepts an ISO 8601 formatted calendar date (`YYYY-MM-DD`) | No | string | null | `2019-08-01`
`end_date` | params | End date (inclusive) requesting location hours. Accepts an ISO 8601 formatted calendar date (`YYYY-MM-DD`)| No | string | null | `2019-08-07`

### Example Requests

#### All libraries, all locations
```
https://library-hours.stanford.edu/libraries.json
```
#### One library, all locations
```
https://library-hours.stanford.edu/libraries/green.json
```

#### One library, one location
```
https://library-hours.stanford.edu/libraries/green/locations/information-center.json
```

#### One library, all locations, date range
```
https://library-hours.stanford.edu/libraries/green.json?from=2019-08-01&to=2019-08-07
```
- If no `start_date` and no `end_date` are provided, the API will provide hours information for the current calendar week.
- If the user provides a `from` parameter an does not provide a `to` parameter, the API will only return information for a single day

## Legacy API (Deprecated)

This service is currently used internal library apps but may not be supported in the future. API consumers should not develop new projects with this API.  

The base url used for this service is `https://library-hours.stanford.edu`.

### Hours for When

```
GET /api/v1/library/{library_id}/location/{location_id}/hours/for/{when}
```

#### Summary
Allows for consumers to request hours for a specific library location at a given time.

#### Parameters

Name | Located In | Description | Required | Type | Default | Example
---- | ---------- | ----------- | -------- | ------ | ------- | ------
`library_id` | url | ID of a library | Yes | string | null | `green`
`location_id` | url | ID of a location within a library | Yes | string | null | `information-center`
`when` | url | Date requesting location hours. Valid values include `today` or an ISO 8601 formatted calendar date `2019-08-22` | Yes | string | null | `2019-08-22`

#### Example request
```sh
$ curl https://library-hours.stanford.edu/api/v1/library/green/location/information-center/hours/for/2019-08-22
```

#### Example response
```json
[
  {
    "id": 228922,
    "day": "2019-08-22",
    "weekday": "Thursday",
    "opens_at": "2019-08-22T10:00:00.000-07:00",
    "closes_at": "2019-08-22T17:00:00.000-07:00",
    "type": "Intersession",
    "notes": "",
    "location_slug": "information-center",
    "location_id": 7,
    "closed": false
  }
]
```
