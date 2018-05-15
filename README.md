## Requirements

This utility requires the Datadog Python Library (https://github.com/DataDog/datadogpy).  

## Example usage:

The dashboard ID is found in the URL when viewing your dashboard.

For Screenboards:

https://app.datadoghq.com/screen/331100/my-screenboard-title

For Timeboards:

https://app.datadoghq.com/dash/345672/my-timeboard-title

Downloading a dashboard as JSON:

`python dash_to_json.py get -d dashboard_id -a your_api_key_here -p your_app_key_here`

`python dash_to_json.py get -d 214520 -a your_api_key_here -p your_app_key_here`

Downloading a dashboard as JSON specifying output file:

`python dash_to_json.py get -d 214520 -f my_screenboard.json -a your_api_key_here -p your_app_key_here`

Creating a dashboard from a local JSON file:

`python dash_to_json.py create -f my_timeboard.json -a your_api_key_here -p your_app_key_here`

## Setting your API/APP key as environment variables

Setting your Datadog API and APP keys as environment variables will eliminate the need to include your keys on the command line when executing script.  Your keys can be found here: https://app.datadoghq.com/account/settings#api

```
export DD_API_KEY=MY_REDACTED_API_KEY
export DD_APP_KEY=MY_REDACTED_APP_KEY
```

## Known issues

As of 5/15 the API doesn't accept process graphs or log and apm datasets on Timeboards.  These graphs will silently be removed when creating a timeboard from JSON.
