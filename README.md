# ecobee

Work in progress. Very hacky

## Setup 

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

A yaml file with these keys:

```yml
api_token: "API token from the application - found under 'Developer'"
auth_code: "Authorization code from Step 1: https://www.ecobee.com/home/developer/api/examples/ex1.shtml"
token_file: "Path to store access and refresh tokens"
```