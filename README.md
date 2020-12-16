# ecobee

Work in progress. Very hacky

## Ecobee Setup 

Create an ecobee developer account [here](https://www.ecobee.com/developers/)
  - 2FA must be disabled on your ecobee account

Log into ecobee

Go to the developer tab

Create an app

Authorize the app

Retrieve the API key from the app you created

Go through the first step [here](https://www.ecobee.com/home/developer/api/examples/ex1.shtml) to retrieve your authorization code

## Notes To Self

Running the `auth.getAuthorizationCode` function will cause you to have to re-add the app with a new PIN, so don't run that

The authorization code returned from GetOAuth can only be used once!

## Configuration File

The configuration file **must** be named `ecobee.yml` and **must** exist in either:

- The directory that you call the binary from (If the binary exists in `/opt/ecobee/ecobee` and you run it from `/var/tmp/`, the config file should be `/var/tmp/ecobee.yml`)

- `$HOME/.ecobee/`

- `/etc/ecobee/`

A yaml file with these keys:

```yml
api_token: "API token from the application - found under 'Developer'"
auth_code: "Authorization code from Step 1: https://www.ecobee.com/home/developer/api/examples/ex1.shtml"
token_file: "Path to store access and refresh tokens"
influxdb_token: "InfluxDB API token"
influxdb_bucket: "bucket name to store data in"
influxdb_org: "org name"
influxdb_uri: "URI to influxdb, including protocol and port"
```

## TODO

Rework refresh token flow to make it automatic
  - This should happen in `ecobee.GetOAuth`

Variable cleanup