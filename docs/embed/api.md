---
id: api
title: Embed
---

Embed is a service that provides an embeddable version of content hosted in the Stanford Digital Repository. Embed uses the [oEmbed](https://oembed.com/) specification for providing an oEmbed response or can embed content directly using an iframe.

## API

The base url used for this service is `https://embed.stanford.edu`.

### oEmbed
```
GET /embed
```
#### Summary
Returns a rich [oEmbed](https://oembed.com/) response for Stanford Digital Repository content.

#### Parameters

Name | Located In | Description | Required | Type | Default | Example
---- | ---------- | ----------- | -------- | ------ | ------- | ------
`url` | query | URL of persistent url location of digital library content | Yes | string | null | `https://purl.stanford.edu/fw090jw3474`
`format` | query | Format requested of response. Valid values are `json` or `xml` | No | string | `json` | `json`
`maxheight` | query | Maximum height of viewer | No | integer | null | `300`
`maxwidth` | query | Maximum width of viewer | No | integer | null | `500`
`hide_title` | query | Hide the title in the viewer | No | boolean | `false` | `true`

#### Example request
```sh
$ curl https://embed.stanford.edu/embed?url=https://purl.stanford.edu/fw090jw3474
```

#### Example response
```json
{
  "type": "rich",
  "version": "1.0",
  "provider_name": "SUL Embed Service",
  "title": "1st Street Arcade San Francisco",
  "height": 420,
  "width": null,
  "html": "<iframe\n        src='https://embed.stanford.edu/iframe?url=https://purl.stanford.edu/fw090jw3474&' height='420px' width='100%'\n        frameborder='0' marginwidth='0' marginheight='0' scrolling='no' allowfullscreen\n      />"
}
```

### iframe
```
GET /iframe
```
#### Summary
Returns an iframe of HTML that can be directly embedded for Stanford Digital Repository content.

#### Parameters

Name | Located In | Description | Required | Type | Default | Example
---- | ---------- | ----------- | -------- | ------ | ------- | ------
`url` | query | URL of persistent url location of digital library content | Yes | string | null | `https://purl.stanford.edu/fw090jw3474`
`maxheight` | query | Maximum height of viewer | No | integer | null | `300`
`maxwidth` | query | Maximum width of viewer | No | integer | null | `500`
`hide_title` | query | Hide the title in the viewer | No | boolean | `false` | `true`

#### Example request
```sh
$ curl https://embed.stanford.edu/iframe?url=https://purl.stanford.edu/fw090jw3474
```

#### Example response
```html
<!DOCTYPE html>
<html>
  <head>
    <script src='https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js'></script>
    <script></script>
  </head>
  <body>
    <div class="sul-embed-container "
      id='sul-embed-object' style='display:none; max-height:420px; max-width:100%;'>
      <div class='sul-embed-body sul-embed-m3' style="max-height: 420px" data-sul-embed-theme="https://embed.stanford.edu/assets/m3-9e06cc02b2cfbcc6025cbbd98225e65b1d4ba45f15501487bebc9576fa69fb8f.css">
        <div
          id='sul-embed-m3'
          class='m3'
          data-m3-uri='https://purl.stanford.edu/fw090jw3474/iiif/manifest'
          data-canvas-id=''
          data-canvas-index=''
          data-hide-title=''
          data-show-attribution='false'
          data-search=''
          data-suggested-search=''
          style='height: 420px; width:100%'>
        </div>
        <script>;jQuery.ajax({url: "https://embed.stanford.edu/packs/js/m3-805fab97844b19976d49.js", cache: true, dataType: 'script'});</script>
      </div>
    </div>
  </body>
</html>
```
