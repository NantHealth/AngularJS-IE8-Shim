# AngularJS 1.4+ IE8 shim 

  - jQuery must be included
  - Tested as of AngularJS 1.4.3
  - Magic

# How it works :: Installation
To start off, you'll need to add the following code at the bottom of your ```<head>``` tag. This code includes the es5 shim, as well as some scripts & styles needed to get IE8 working like usual.

```html
<!--[if IE 8]>
    <!-- you can use a CDN or host it locally -->
    <script src="//cdnjs.cloudflare.com/ajax/libs/es5-shim/4.0.5/es5-shim.min.js"></script>
    <script>
        document.createElement('ng-view');
        document.createElement('ng-form');
        <!-- ng-form is needed if you're using WebForms -->
    </script>
    <style>
        .ng-hide { display: none !important; }
        [ng-cloak] { display:none !important; }
    </style>
<![endif]-->
```

##### Now, in the end of your body tag where the rest of your JavaScript is, add the Angular IE8 shim:
#
```html
<script src="Angular-JS-ie8-shim.min.js" />

<!-- Make sure you include jQuery 1.* somewhere here as well for iE8 -->

```



##### THEN, you can add all your angularJS files, etc.
##### - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
##
##

# Tips (since we care about IE8)

The usual IE8 gotchas apply, as well as some angular-specific ones.

* Be careful of IE8 keywords such as ```finally / catch / continue / etc ```
* Use ATTRIBUTE directives ```<div my-directive />``` (unless you want to manually add all the document.createElement tags
* Make sure to test all directives specifically in IE8, sometimes directive inception breaks down in IE8.

