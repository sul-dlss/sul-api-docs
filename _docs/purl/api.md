---
id: api
title: PURL
---

PURL (Persistent URL) is a service that provides a persistent URL to content in the Stanford Digital Repository. We guarantee that content will be available in some form at this URL. The PURL platform is the basis for access and citation of content and uses other APIs provided by the Stanford Libraries including [embed](/docs/embed/api) and [IIIF](/docs/iiif/api).

## API

### Persistent, citable access

The base url used for this service is `https://purl.stanford.edu`.

#### Summary

Will return an HTML response for an item. A web browser with JavaScript enabled will receive an enhanced version of this content.

```
GET /{id}
```

#### Parameters

Name | Located In | Description | Required | Type | Default | Example
---- | ---------- | ----------- | -------- | ------ | ------- | ------
`id` | url | The ID of a digital object | Yes | string | null | `ab123cd4567`

#### Example Requests

```
https://purl.stanford.edu/wy323vc0101 # the same as https://purl.stanford.edu/wy323vc0101.html
```

### Public XML

The base url used for this service is `https://purl.stanford.edu`.

#### Summary

Will return public metadata about the object in an XML representation. Includes the following parts representing a digital object:

1. Identifying information
1. Object relationship information
1. Content information
1. Content availability information
1. Bibliographic information
1. Version information
1. Release information
1. Thumbnail information

```
GET /{id}.xml
```

#### Parameters

Name | Located In | Description | Required | Type | Default | Example
---- | ---------- | ----------- | -------- | ------ | ------- | ------
`id` | url | The ID of a digital object | Yes | string | null | `ab123cd4567`

#### Example Requests

```
https://purl.stanford.edu/wy323vc0101.xml
```

#### Example Response (truncated)

```xml
<publicObject objectId="druid:wy323vc0101" published="datetime">
  <identityMetadata>
   :
  </identityMetadata>
  <versionMetadata>
   :
  </versionMetadata>
  <rdf:RDF>
   :
  </rdf:RDF>
  <contentMetadata>
   :
  </contentMetadata>
  <rightsMetadata>
   :
  </rightsMetadata>
  <oai_dc:dc>
   :
  </oai_dc:dc>
</publicObject>
```

### Public MODS

The base url used for this service is `https://purl.stanford.edu`.

#### Summary

Will return public metadata about the object in an MODS xml representation.

```
GET /{id}.mods
```

#### Parameters

Name | Located In | Description | Required | Type | Default | Example
---- | ---------- | ----------- | -------- | ------ | ------- | ------
`id` | url | The ID of a digital object | Yes | string | null | `ab123cd4567`

#### Example Requests

```
https://purl.stanford.edu/wy323vc0101.mods
```

#### Example Response (truncated)

```xml
<mods xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://www.loc.gov/mods/v3" version="3.6" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-6.xsd">
  <titleInfo>
   :
  </titleInfo>
  <name>
   :
 </name>
  <language>
   :
  </language>
  <physicalDescription>
   :
  </physicalDescription>
  ...
</mods>
```
