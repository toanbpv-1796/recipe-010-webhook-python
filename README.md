# Webhook-Python recipe
This directory includes the source for the Python Webhook recipe and enables it to be run on a free Heroku server.

The /app directory holds the complete example

The top level files are used to manage and configure the example on [Heroku](https://www.heroku.com/).

## Run the recipe on Heroku
The recipe source, as is, works on the [Heroku](https://www.heroku.com/) using the free service level. No credit card needed!

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

Click the Deploy button, then enter your DocuSign Developer Sandbox credentials on the form in the Heroku dashboard. Then press the View button at the bottom of the dashboard screen when it is enabled by the dashboard.

First, sign up for an account at [heroku.com](http://heroku.com) and install the heroku toolbelt.

Then:

```sh
$ git clone this_repo 010-webhook-python
$ cd 010-webhook-python
$ heroku create
$ git push heroku master
  # Note that the process will slow down when it installs lxml since that library requires compilation
  # The following steps will set environment values. Do not include spaces around the = sign:
$ heroku config:set DS_USER_EMAIL=DocuSign_email
$ heroku config:set DS_USER_PW=DocuSign_password
$ heroku config:set DS_INTEGRATION_ID=DocuSign_integration_key	
$ heroku ps:scale web=1
$ heroku open
```

Your web browser should now open and show the app. Reload the web page if the app is not shown.

## Run the recipe on your own server

### Get Ready
Your server needs Python 2.7 or later

Your server **must** have an address that is visible and accessible from the public internet. Unless that is the case, the DocuSign platform will not be able to post the notification messages *to* your server.

You need an email address and password registered with the free DocuSign Developer Sandbox system. You also need a free Integration Key for your DocuSign developer account. See the [DocuSign Developer Center](https://www.docusign.com/developer-center) to sign up.

### How to do it
```sh
% pip install -r requirements.txt
% python run.py
```

