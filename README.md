# react-native-periculum

Periculum library is a powerful & easy to use credit score library for Android.
The library gives you credit score information for your customer. No stress :)

## Badges

[![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/tterb/atomic-design-ui/blob/master/LICENSES)

## Installation

Add react-native-periculum to your project by running;

Yarn

```bash
yarn add react-native-periculum
```

NPM

```bash
npm install react-native-periculum
```

&nbsp;

## Info

You need to have a [periculum](https://www.periculum.io/) account for this plugin to work. And also install the following packages for the plugin to work perfectly.

- react-native-device-info
- react-native-get-location
- react-native-get-sms-android
- react-native-permissions

&nbsp;

## Android Permissions

Please make sure you add the following android permissions in your AndroidManifest.xml file

```bash
<uses-permission android:name="android.permission.READ_SMS" />
<uses-permission android:name="android.permission.WRITE_SMS" />
<uses-permission android:name="android.permission.SEND_SMS" />
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>
```

&nbsp;


## Periculum Analytics V1

How to use the Periculum analytics method.
If you are using the V1 SDK methods then do the following:

Example:

```javascript
import React from 'react';
import {analyticsRequestV1} from 'react-native-periculum';

await analyticsRequestV1(publicKey, statementName, customerMobile, customerBvn)
  .then(result => {
    console.log({result});
  })
  .catch(error => {
    console.log({error});
  });
```

## Periculum Analytics V1 Parameters

| Name           | Description                                             | Type   | Required|
| -------------- | ------------------------------------------------------- | ------ | --------|
| publickey      | Required. Public Key attached to account                | String | Yes     |
| statementName  | unique statement reference                              | String | No      |
| customerMobile | Required. customer phone number                         | String | Yes     |
| customerBvn    | customer bvn                                            | String | No      |


## Response 
The response will contain a set of insight keys. You can send these to your backend server. The backend server can use it's client credentials to obtain all the insight details for each key from the Insight API.
&nbsp;
&nbsp;

## Periculum Analytics V2

How to use the Periculum Analytics V2 method.
If you are using the V2 SDK methods then do the following:

Example:

```javascript
import React from 'react';
import {analyticsRequestV2} from 'react-native-periculum';

await analyticsRequestV2(publicKey, statementName, customerMobile, customerBvn)
  .then(result => {
    console.log({result});
  })
  .catch(error => {
    console.log({error});
  });
```

## Periculum Analytics V2 Parameters

| Name           | Description                                             | Type   | Required |
| -------------- | ------------------------------------------------------- | ------ | --------|
| publickey      | Required. Public Key attached to account                | String | Yes     |
| statementName  | unique statement reference                              | String | No      |
| customerMobile | Required. customer phone number                         | String | Yes     |
| customerBvn    | customer bvn                                            | String | No      |


## Response 
Insights will return an overview key.
You can send this overview key back to your backend server. Your backend server will use it's client credentials to make a to the insights mobile v2 endpoints for details related to the overview key.

&nbsp;
&nbsp;

## Updating an existing mobile V2 Analytics

If you have a previously generated mobile v2 overview key, you can update it with a new SDK data. to do this make the following call:

Example:

```javascript
import React from 'react';
import {patchV2} from 'react-native-periculum';

patchV2(
  publicKey,
  statementKey,
  identificationData,
)
  .then(result => {
    console.log(result);
  })
  .catch(error => {
    console.log(error);
  });
```

## Updating an existing mobile V2 Analytics parameters

| Name               | Description                                           | Type   | Required |
| ------------------ | ----------------------------------------------------- | ------ | -------- |
| publicKey          | Public Key attached to the client account             | String | Yes      |
| statementKey       | Unique statement reference                            | int    | Yes      |
| identificationData | Array of object with keys of IdentifierName and Value | array  | Yes      |


## Response 
Insights will update the previous overview key data with the latest data.
You can use the overview key in your backend server with it's client credentials to make a call to the insights mobile v2 endpoints for details related to the overview key.

&nbsp;
&nbsp;

## Setup

In order to utilize any of the SDK methods, you must have a public key. If you have not obtained your client public key, then you should contact Periculum standard support channel (email support@periculum.io).


&nbsp;

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)
