#  jQuery iframe auto height plugin

## Shot Summary
Based on "iframe autoheight jQuery Plugin" code from [https://github.com/house9/jquery-iframe-auto-height]([https://github.com/house9/jquery-iframe-auto-height])

The plugin will resize an iframe to the height of its contents

### Differences from the original version:
  added new options:
      * defaultHeight: integer
        * Default is 0
        * Unit is pixels
        * Sets the iframe height to this value if catch exception (e.g. cross domain policy fail)
        * Example: `$('iframe').iframeAutoHeight({defaultHeight: 200});`
    * timeInterval: integer
      * Default is -1
      * if timeInterval == -1: resize after iframe loads; if timeInterval > 0: plugin will resized after each timeInterval milliseconds;
      * Example: `$('iframe').iframeAutoHeight({timeInterval: 500});`


## Usage:

* include jquery in your page
* include the latest version;
* use the variable jQuery or its alias $ and pass a selector that matches one or more iframes

`jQuery('iframe').iframeAutoHeight();` will resize all iframes on the page

`$('#test-iframe').iframeAutoHeight();` will resize only one iframe

code can be called from within $(document).ready

```
<!-- with document ready, most likely in the html head -->
<script>
  $(document).ready(function () {
    $('iframe').iframeAutoHeight({debug: true});
  });
</script>
```

### Options

* callback: function
  * Default empty function
  * Optionally define a callback function (in this case inline) that will do something with the callbackObject.newFrameHeight value. This can for instance be used with easyXDM to alert another domain that the frame has changed height. (See http://github.com/oyvindkinsey/easyXDM.)
  * Example: `$('iframe').iframeAutoHeight({callback: function(callbackObject) {alert(callbackObject.newFrameHeight);} });`
* debug: boolean
  * Default is false
  * Will log some internal information to the console, if available
  * Example: `$('iframe').iframeAutoHeight({debug: true})`
* heightOffset: integer
  * Default is 0
  * Unit is pixels
  * Optionally add some buffer to the bottom
  * Example: `$('iframe').iframeAutoHeight({heightOffset: 20});`
* minHeight: integer
  * Default is 0
  * Unit is pixels
  * Sets the iframe height to this value if the calculated value is less
  * Example: `$('iframe').iframeAutoHeight({minHeight: 200});`
* defaultHeight: integer
  * Default is 0
  * Unit is pixels
  * Sets the iframe height to this value if catch exception (e.g. cross domain policy fail)
  * Example: `$('iframe').iframeAutoHeight({defaultHeight: 200});`
* timeInterval: integer
  * Default is -1
  * if timeInterval == -1: resize after iframe loads; if timeInterval > 0: plugin will resized after each timeInterval milliseconds;
  * Example: `$('iframe').iframeAutoHeight({timeInterval: 500});`

## Summary:

Based on "iframe autoheight jQuery Plugin" code from [https://github.com/house9/jquery-iframe-auto-height]([https://github.com/house9/jquery-iframe-auto-height])

The plugin will resize an iframe to the height of its contents

When viewing code locally, i.e. file:///, Google chrome will throw security errors; (use "-allow-file-access-from-files" to avoid testing)
Works fine in Firefox locally and should work ok in all browsers when served from the same domain.

Current Version: 0.1

## License:

The plugin: js/jquery.iframe-auto-height.plugin.js

* The Unlicense (aka: public domain)

See specific license for any other code included, i.e. jquery


## Changelog:

0.1 / 2012-04-05 / Initial release

* added jquery.iframe-auto-height.plugin.js

## Known Issues

* IE may hang when page has many iframes and using setInterval > 0;