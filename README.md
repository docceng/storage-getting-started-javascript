# Google Cloud Storage JavaScript Sample Application

## Description
This is a simple web-based example of calling the Google Cloud Storage API
in JavaScript.

## Summary
This sample app consists of one monolithic file (index.html) that includes the
HTML and JavaScript code needed to support the following capabilities:

- Authorize access to a Google Cloud Storage account using OAuth 2.0.

- Accept a user supplied bucket name and use the Google Cloud Storage
  JSON API to obtain and display a formatted list of bucket contents.

Because everything is embedded in one file, this application can be loaded
directly into a web browser from a file on a local hard drive - there's no
need to setup a web server.

Google Cloud Storage documentation is available at
http://developers.google.com/storage/

## Setup
PREREQUISITE: Enable Google Cloud Storage for your project on the Google
APIs console and setup billing so that you'll be authorized to use
Google Cloud Storage with this app. See this page for more details:
https://developers.google.com/storage/docs/signup.

1. Download the two files: index.html and README.txt (this file).

2. Open the index.html file with a text editor and make the following changes:
- Create a client ID for Web Applications via the "API Access" tab
on the APIs console (https://code.google.com/apis/console/#access).

- Again on the APIs console page, add your JavaScript origin (the root
URL from which your application will run) to the JavaScript origins
section of your Client ID on the API Access tab. If you're not sure
what this is, you can skip this step and continue with the remaining
steps below - in that case, when you get to the point where you try
the app, you'll see a dialog showing "Error: origin_mismatch". Expand
the error message and you should see request details like these:

Request Details
---------------
- scope=https://www.googleapis.com/auth/devstorage.full_control
- response_type=token
- access_type=online
- redirect_uri=postmessage
- approval_prompt=auto
- proxy=oauth2relay1195330867
- origin=[redacted]
- state=501277282
- client_id=[redacted]
- authuser=0

The value shown for the "origin" field is the one you'll want to
administer in the JavaScript origins section on the APIs console.

- In index.html, search and replace all strings starting with "YOUR_"
with their associated values.

3. Save the changes to index.html.

## Usage
Open index.html in a web browser and click the "Authorize" button near the
top left of the page. This will request access to your Google account.
Access will be valid for about an hour.

Enter a valid bucket name in the bucket name text field and press the
button to obtain a listing of the bucket contents. You should see a
formatted report appended to the bottom of the page with the results
of the bucket list.
