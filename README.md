# HAX and Web components PHP Library

## Install
Get polymer cli installed prior to usage of this (and (yarn)[https://yarnpkg.com/lang/en/docs/install/#mac-stable] / an npm client of some kind)
```bash
$ yarn global add polymer-cli
# or...
$ npm install -g polymer-cli
```
Then clean up the asset list you actually want to use in production. A large list has been added to this repo for you in `build.js`.
## HAXService
This is a series of helpers for integrating HAX with PHP based systems. Specifically, this helps in getting the HAX Appstore specification output. Appstore is a JSON blob which expresses to HAX how to connect to various services. This helps with integrating with PHP based backends so they can serve up API keys as well as extend what comes across.

## WebComponentsService

WebComponentsService also helps get the polyfill applied in a uniform way
```php
// require the service
require WebComponentsService.php;
$WCService = new WebComponentsService();
// return a string to your template / front end some how while passing in
// the path to where the component build directory has been placed.
return $WCService->applyWebcomponents('location/of/your/components/');
```
In Drupal this looks like `$WCService->applyWebcomponents("sites/all/libraries/webcomponents");`

You can see this library implemented with some additional customizations in the following frameworks:
- GravCMS - https://github.com/elmsln/grav-plugin-hax/blob/master/hax.php#L79-L91
- Drupal 6 - https://cgit.drupalcode.org/hax/tree/hax.module?h=6.x-3.x#n193
- Drupal 7 - https://cgit.drupalcode.org/hax/tree/hax.module?h=7.x-3.x#n292
- Drupal 8 - https://cgit.drupalcode.org/hax/tree/hax.module?h=8.x-3.x#n292
- Backdrop - https://github.com/backdrop-contrib/hax/blob/1.x-3.x/hax.module#L221-L236
