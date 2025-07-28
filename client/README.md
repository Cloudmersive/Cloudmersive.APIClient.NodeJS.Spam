# cloudmersive-spamapi-client

CloudmersiveSpamapiClient - JavaScript client for cloudmersive-spamapi-client
Easily and directly scan and block spam security threats in input.
[Cloudmersive Spam Detection API](https://cloudmersive.com/spam-detection-api) provides advanced AI spam detection capabilities.

- API version: v1
- Package version: 2.0.0


## Installation

### For [Node.js](https://nodejs.org/)

#### npm

To publish the library as a [npm](https://www.npmjs.com/),
please follow the procedure in ["Publishing npm packages"](https://docs.npmjs.com/getting-started/publishing-npm-packages).

Then install it via:

```shell
npm install cloudmersive-spamapi-client --save
```

##### Local development

To use the library locally without publishing to a remote npm registry, first install the dependencies by changing 
into the directory containing `package.json` (and this README). Let's call this `JAVASCRIPT_CLIENT_DIR`. Then run:

```shell
npm install
```

Next, [link](https://docs.npmjs.com/cli/link) it globally in npm with the following, also from `JAVASCRIPT_CLIENT_DIR`:

```shell
npm link
```

Finally, switch to the directory you want to use your cloudmersive-spamapi-client from, and run:

```shell
npm link /path/to/<JAVASCRIPT_CLIENT_DIR>
```

You should now be able to `require('cloudmersive-spamapi-client')` in javascript files from the directory you ran the last 
command above from.

#### git
#
If the library is hosted at a git repository, e.g.
https://github.com/GIT_USER_ID/GIT_REPO_ID
then install it via:

```shell
    npm install GIT_USER_ID/GIT_REPO_ID --save
```

### For browser

The library also works in the browser environment via npm and [browserify](http://browserify.org/). After following
the above steps with Node.js and installing browserify with `npm install -g browserify`,
perform the following (assuming *main.js* is your entry file, that's to say your javascript file where you actually 
use this library):

```shell
browserify main.js > bundle.js
```

Then include *bundle.js* in the HTML pages.

### Webpack Configuration

Using Webpack you may encounter the following error: "Module not found: Error:
Cannot resolve module", most certainly you should disable AMD loader. Add/merge
the following section to your webpack config:

```javascript
module: {
  rules: [
    {
      parser: {
        amd: false
      }
    }
  ]
}
```

## Getting Started

Please follow the [installation](#installation) instruction and execute the following JS code:

```javascript
var CloudmersiveSpamapiClient = require('cloudmersive-spamapi-client');

var defaultClient = CloudmersiveSpamapiClient.ApiClient.instance;

// Configure API key authorization: Apikey
var Apikey = defaultClient.authentications['Apikey'];
Apikey.apiKey = "YOUR API KEY"
// Uncomment the following line to set a prefix for the API key, e.g. "Token" (defaults to null)
//Apikey.apiKeyPrefix['Apikey'] = "Token"

var api = new CloudmersiveSpamapiClient.SpamDetectionApi()

var opts = { 
  'body': new CloudmersiveSpamapiClient.SpamDetectionAdvancedRequest() // {SpamDetectionAdvancedRequest} Spam detection request
};

var callback = function(error, data, response) {
  if (error) {
    console.error(error);
  } else {
    console.log('API called successfully. Returned data: ' + data);
  }
};
api.spamDetectTextStringAdvancedPost(opts, callback);

```

## Documentation for API Endpoints

All URIs are relative to *https://localhost*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*CloudmersiveSpamapiClient.SpamDetectionApi* | [**spamDetectTextStringAdvancedPost**](docs/SpamDetectionApi.md#spamDetectTextStringAdvancedPost) | **POST** /spam/detect/text-string/advanced | Perform advanced AI spam detection and classification against input text string.  Analyzes input content as well as embedded URLs with AI deep learnign to detect spam, phishing and other unsafe content.  Uses 25-100 API calls depending on model selected.
*CloudmersiveSpamapiClient.SpamDetectionApi* | [**spamDetectTextStringPost**](docs/SpamDetectionApi.md#spamDetectTextStringPost) | **POST** /spam/detect/text-string | Perform AI spam detection and classification against input text string.  Analyzes input content as well as embedded URLs with AI deep learnign to detect spam, phishing and other unsafe content.  Uses 25-75 API calls depending on model selected.


## Documentation for Models

 - [CloudmersiveSpamapiClient.SpamDetectionAdvancedRequest](docs/SpamDetectionAdvancedRequest.md)
 - [CloudmersiveSpamapiClient.SpamDetectionAdvancedResponse](docs/SpamDetectionAdvancedResponse.md)
 - [CloudmersiveSpamapiClient.SpamDetectionRequest](docs/SpamDetectionRequest.md)
 - [CloudmersiveSpamapiClient.SpamDetectionResponse](docs/SpamDetectionResponse.md)


## Documentation for Authorization


### Apikey

- **Type**: API key
- **API key parameter name**: Apikey
- **Location**: HTTP header

