# Aruba Central Token Refresh Tool


## Getting Started
To start, please login to Aruba Central and create an API account. To do this go to Account Home -> API Gateway -> System Apps & Tokens, then click on the + sign to "Add Apps and Tokens". 

You'll also need to create a ``config.yml`` file. There's a ``config.yml.orig`` that you should use as a template or just rename ```config.yaml.org``` to ```config.yml```. You'll need the following info:

URL for access the Aruba Central API for your region
customer_id for identify who you are as a customer
client_id for identify your API ID
client_secret for accessing your API
username
password

Once you have created your config.yml with the information for your account, run the following command.

```aruba_token_refresh```

This will download or create a new access_token and save them in default.token.json (or companyname.token.json). 


## SSO
If you have SSO setup on your account, you'll need to create a new Central login that doesn't use SSO. I use an email alias for my coporate account that isn't using the same domain as my SSO account. Others have used personal accounts. This account is only used to generate or refresh access_tokens.

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

if you plan to run it frequently, then install the necessary python modules and install the ``aruba_refresh_token`` as a python module.


## Additional Features
If you have more than one API account that you can to refresh token for, you can set them up in the config file as follows:

```
PickleShoes:
   url: https://apigw-prod2.central.arubanetworks.com
   envapi:  prod
   customer_id: 1234567...
   client_id: 34567...
   client_secret: 9876543...

```

Once the entry above is saved. You can then execute the refresh for the above account by typing:

```
aruba_refresh_token PickleShoes
```

This will then refresh the token or request an authcode and access token for that account you specified.

## Future Features
Plan on adding code to recreate the access and refresh tokens after the refresh tokens expires after 14 days. The code is already written. I just need to build the CLI for it.

## Authors

* **Michael Rose Jr.** - [GitHub](https://github.com/michaelrosejr)


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details



