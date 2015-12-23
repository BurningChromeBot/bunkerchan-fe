[8TailedLynx](https://gitgud.io/obongo/8TailedLynx) is a frontend for the [Lynx Chan](https://gitgud.io/LynxChan/LynxChan) [LynxChan Group](https://gitgud.io/groups/LynxChan) imageboard software that strives to look like [8chan](8ch.net). Currently in use on [endchan](http://endchan.xyz) [InfinityNow Dev Group](https://gitgud.io/groups/InfinityNow) and a demo site at [HambubgerChan](http://hambubger.com)

Install by cloning into your LynxChan src/ directory. Make sure to check out the correct tag.

To personalize your chan please replace the logo and favicon in static/ and the default banner in templates/. You can change default thumbnails and spoilers by editing templateSettings.json to point their entries to other files.

The favicon in the static directory is served from static.{your.domain} and will need to be uploaded into MongoDB manually. To do this you need to get the 
mongofiles tool and run

> mongofiles -h localhost -d {dbName} -p 27017 -l {/path/to/yourfavicon} put /favicon.ico


This front end currently requires you to set the URI of the overboard as "overboard".

If you want do disable anything, just find its ID or CLASS from the HTML template and add it to the CSS file with {display: hidden}, which will remove it from the layout.

Licensed under the MIT License. All current JavaScript is MIT licensed from Stephen Lynx.

You need to run the set domain script with ./set-domain.sh {your-domain} for the HTML templates and CSS to work.
For the javascript to work, you will have to create a file named settings.js in the static directory and declare the following variables in it:
* VERBOSE: if true, it will print incoming and outcoming data from the api.
* DISABLE_JS: if true, javascript will not be used.
* API_DOMAIN: domain for the json api.

Example:
```
var VERBOSE = false;
var DISABLE_JS = false;
var API_DOMAIN = 'http://api.{your-domain}/';
```
Don't forget to do this.
