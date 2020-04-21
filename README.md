# heroku-buildpack-telegraf
A simple heroku buildpack to download, deploy and launch Telegraf on your dynos

This buildpack downloads the latest Telegraf release (at the time of writing, 1.14.1), extracts it on your dyno and starts it via a .profile.d script.

## Installation
First create a `telegraf.conf` file inside `.heroku` folder in your app's directory. Take a look at [the docs](https://github.com/influxdata/telegraf/blob/master/docs/CONFIGURATION.md) for instructions on generating and modifying a telegraf configuration file.

Also, you can configure your `telegraf.conf` file location using `TELEGRAF_CONF` environment variable.

Then add the buildpack to the list of heroku buildpacks:

    heroku buildpacks:add --index 1 https://github.com/odarriba/heroku-buildpack-telegraf.git

**Note:** for production usage, pointing to git using a commit SHA identifier is highly recommended.
