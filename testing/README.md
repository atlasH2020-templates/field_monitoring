
# Testing

## Pre-requisites
Install base testing environment as described in https://github.com/atlasH2020/testing.

## Setup
Download the [field_monitoring.postman_collection.json](./field_monitoring.postman_collection.json) collection and import it in postman.

## Usage
Configure the `field_monitoring_url` variable in the atlas-h2020-variables environment. You may obtain this URL by executing the registry API `get service api` request after manually setting the `service_name` registry collection variable to an existing ATLAS service, or by manually entering the URL to a service you are developing, if it is not yet registered.

You will also need to obtain a refresh token which you must save in the `field_monitoring_token` environment variable (see https://github.com/atlasH2020/testing#obtaining-a-service-token).

You can now experiment with the field_monitoring API.
