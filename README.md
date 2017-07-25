# Spinnaker Canary UI

## Prerequisites

Make sure that [node](http://nodejs.org/download/) and [yarn](https://yarnpkg.com/en/docs/install) are installed on your
system. The minimum versions for each are listed in `package.json`.

## Quick Start

Run the following commands (in the root directory) to get all dependencies installed in Deck and to start the server:

* `yarn`
* `yarn start`

The app will start up on [localhost:9000](localhost:9000).

## Environment variables

* `API_HOST` overrides the default Spinnaker API host.
* `LIVE_CALLS` allows the UI to interact with the API host for canary config-related calls.

For example, `API_HOST=https://localhost:8084 LIVE_CALLS=true yarn start` will run Deck 
with `https://localhost:8084` as the API host.

## Testing

To run the tests within the application, run `yarn run test`.

#### NOTE
Developing things locally? You will want to run [gate](https://github.com/spinnaker/gate) 
locally (which runs on port 8084) and [kayenta](https://github.com/Netflix-Skunkworks) (which runs on port 8090).


You also will need to provide the following fields to your `gate-local.yml` config:

```
services:
  kayenta:
    enabled: true
    canaryConfigStore: true
    baseUrl: http://localhost:8090
```
