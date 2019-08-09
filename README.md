# sul-api-docs

Documentation site for Stanford Libraries public API's. This static site is built using [docusaurus](https://docusaurus.io).

## Installation

After cloning the repository change directory to `website`.

```sh
$ cd website
```

Install dependencies.

```sh
$ npm install
```

Start server

```sh
$ npm start
```

## Adding a new API

To add a new service API, create a new directory under `./docs` as the service name.

Then create a new file under that directory `api.md`.

`api.md` should look something like this:

```md
    ---
    id: api
    title: Nice name of service
    ---

    Overall description of service.

    ## API

    The base url used for this service is `https://foo.stanford.edu`.

    ### Name of API endpoint / service
    ```
    GET /example/:foo?param=bar
    ```
    #### Summary
    

    #### Parameters

    Name | Located In | Description | Required | Type | Default | Example
    ---- | ---------- | ----------- | -------- | ------ | ------- | ------
    `foo` | url | Description | Yes | string | null | `foo`
    `bar` | query | Description | No | string | `bar` | `bar`

    #### Example request
    ```sh
    $ curl https://foo.stanford.edu/foo?param=bar
    ```

    #### Example response
    ```json
    {
      "response": "body"
    }
    ```
    
    ### Name of API endpoint / service
    ...
```
