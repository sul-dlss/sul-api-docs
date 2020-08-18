---
id: api
title: Digital Stacks
---

Digital Stacks, or "Stacks", provides delivery services to access content in the Stanford Digital Library. This takes the form of streaming downloads of files, image web services, or streaming media.

## API

### Downloading a file

The base url used for this service is `https://stacks.stanford.edu`.

#### Summary

Will return binary download of content that from the Stanford Digital Library. Has access controls enabled so only authorized requests are allowed.

** [Cross-Origin Resource Sharing (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) is enabled for this API.
** This API advertises [HTTP Accept headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept) enabling partial and resumable downloads.

```
GET /file/{id}/{file_name}
```

#### Parameters
Name | Located In | Description | Required | Type | Default | Example
---- | ---------- | ----------- | -------- | ------ | ------- | ------
`id` | url | The ID of a digital object | Yes | string | null | `ab123cd4567`
`file_name` | url | File name with extension | Yes | string | null | `test.pdf`

#### Example Requests

```
https://stacks.stanford.edu/file/qq826dq9111/neighborhood-stats_2661_20130512.csv
```

#### Example of using this

This example by Elijah Meeks demonstrates how a web application can use Digital Stacks to power a visualization.

http://bl.ocks.org/emeeks/757e699fed2658bcb42b


### Downloading all files for a given object

The base url used for this service is `https://stacks.stanford.edu`.

#### Summary

Will return a binary download of all accessible content associated with a given object from the Stanford Digital Repository in a zip archive.

```
GET /object/{id}
```

#### Parameters
Name | Located In | Description | Required | Type | Default | Example
---- | ---------- | ----------- | -------- | ------ | ------- | ------
`id` | url | The ID of a digital object | Yes | string | null | `ab123cd4567`

#### Example Requests

```
https://stacks.stanford.edu/object/qq826dq9111
# Will return a download of qq826dq9111.zip containing two files.
```

### IIIF Services
Digital Stacks also serves some [IIIF](https://iiif.io/technical-details/) web services for Stanford Libraries. For more information about this implementation, see: [IIIF](/docs/iiif/api#iiif-image-v2-api)
