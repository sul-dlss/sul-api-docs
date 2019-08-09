---
id: api
title: IIIF
---
The [International Image Interoperability Framework (IIIF)](https://iiif.io) is a set of shared application programming interface (API) specifications for interoperable functionality in digital image repositories. The IIIF is comprised of and driven by a community of libraries, museums, archives, software companies, and other organizations working together to create, test, refine, implement and promote the IIIF specifications. Using JSON-LD, linked data, and standard W3C web protocols such as Web Annotation, IIIF makes it easy to parse and share digital image data, migrate across technology systems, and provide enhanced image access for scholars and researchers. In short, IIIF enables better, faster and cheaper image delivery.

## API

### Presentation v2 API

The base url used for this service is `https://purl.stanford.edu`.

#### Summary

```
GET /{id}/iiif/manifest
```

#### Parameters
Name | Located In | Description | Required | Type | Default | Example
---- | ---------- | ----------- | -------- | ------ | ------- | ------
`id` | url | The ID of a digital object | Yes | string | null | `ab123cd4567`

#### Example Requests

##### Paged book
```
https://purl.stanford.edu/wy323vc0101/iiif/manifest
```

### Presentation v3 API (ALPHA)

This service is currently used internal library apps, but is likely to change as the IIIF Presentation API v3 spec is finalized. API consumers should not develop new projects with this API.  

The base url used for this service is `https://purl.stanford.edu`.

#### Summary
```
GET /{id}/iiif3/manifest
```
#### Parameters

Name | Located In | Description | Required | Type | Default | Example
---- | ---------- | ----------- | -------- | ------ | ------- | ------
`id` | url | The ID of a digital object | Yes | string | null | `ab123cd4567`

#### Example request

##### Paged book
```
https://purl.stanford.edu/wy323vc0101/iiif3/manifest
```

### IIIF Image v2 API

The base url used for this service is `https://stacks.stanford.edu`. The [IIIF Image API specification](https://iiif.io/api/image/2.1/#terminology) has details about how to construct IIIF Image API requests.

#### Example Requests

##### Full size image
```
https://stacks.stanford.edu/image/iiif/wy323vc0101%2F36105115643962_0002/full/full/0/default.jpg
```
