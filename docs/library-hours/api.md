---
id: api
title: Library Hours
---
Library Hours is an application that allows Stanford Libraries to set hours of operation for various libraries on campus. It also provides an API in which consumers can query information about the hours of operations.


## API

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
