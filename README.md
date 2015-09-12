# AngularJS 1.4+ IE8 shim 

# Prereqs

  - jQuery (1.*) must be included for IE8 (you can put this within IE Conditional tags if you want)
  - ES5 Shim must be included
  
# General

  - Tested as of the latest AngularJS version # 1.4.5
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

```html
<script src="angular.1.4.5.min.js" />
<!-- etc etc -->
```

##### - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
##
##

# Tips (since we care about IE8)

The usual IE8 gotchas apply, as well as some angular-specific ones.

* Be careful of IE8 keywords such as ```finally / catch / continue / etc ```

    * For example, promises / $q with the object method ```promise.finally()``` will break.
    * Any custom object methods such as myObject.continue() will break as well.

    * If you need to use these, simply use Array notation: 
    ``` promise['finally'](function () { }); ```
    ``` myObject['continue'](); ```

* Use ATTRIBUTE (restrict: 'A') directives ```<div my-directive />``` (unless you want to manually add each individual  document.createElement tags. (I recommend only making extremely global ones 'E' element directives.

* Make sure to test all directives specifically in IE8, sometimes directive inception breaks down in IE8.

