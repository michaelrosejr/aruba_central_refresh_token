# Aruba Central Token Refresh Tool


## Getting Started
To start, please login to Aruba Central and create an API System Token Under Maintenance -> API Gateway. Once done, download the token and save it as ``defualt.token.json`` in the directory where you installed this script.

You'll also need to create a ``config.yml`` file. There's a ``sample.config.yml`` that you should use as a template. You'll need the following info:

URL for access the Aruba Central API for your region
customer_id for identify who you are as a customer
client_id for identify your API ID
client_secret for accessing your API

once done, run aruba_refresh_token and it will refresh your Aruba Central token and post the access_token and refresh_token on the scren.

## Start-Up
Onces the ``default.token.json`` and ``config.yml`` files have been created. 

For those that don't want to install the Python modules used by this script, you can run the following command:

```
pipenv run aruba_token_refresh
```

You can also run it by entering the pipenv shell:

```
pipenv shell
aruba_token_refresh
```

## Authors

* **Michael Rose Jr.** - [GitHub](https://github.com/michaelrosejr)


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details



