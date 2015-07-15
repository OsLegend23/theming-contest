## Sencha App Theming Contest

### Requirements
* [Download Ext JS 6] (https://www.sencha.com/products/extjs/evaluate/)
* [Download CMD] (https://www.sencha.com/products/extjs/cmd-download/)
* [Download Sencha Inspector Early Access] (http://pages.sencha.com/Inspector-Early-Access.html)



### Getting started with Feed Viewer App

* Create a workspace
```
sencha -sdk {path/to/Ext-JS-SDK}  generate workspace theming-workspace
```
* Fork/Clone/Download this Feed Viewer sample application and Extract it in theming-workspace

* Build the Feed Viewer sample application
```
sencha -sdk {path/to/Ext-JS-SDK} app build development
```

* Start web server and watch changes
```
sencha app watch
```

* View the Feedviewer sample app in browser with platform tag. It will show view with classic toolkit
```
http://localhost:1841/?platformTags=fashion:true
```

* To view the modern toolkit based view, in Chrome developer tools, toggle device mode icon and select mobile phone


### Connect Feed Viewer app to Sencha Inspector

* Create a bookmark in your browser with name "Sencha Inspector" and copy the following code into the URL:
```
javascript:!function(a,b){var a=a||3e3,b=b||"http://localhost",c=b+":"+a+"/inspector.js",d=function(a,c){var d=document.createElement("script");d.type="text/javascript",d.src=a,document.addEventListener("load",function(){"undefined"!=typeof Ext&&"undefined"!=typeof Ext.onReady&&Ext.onReady(function(){if(window.SenchaInspector){var a=document.head.getAttribute("data-senchainspectorport");SenchaInspector.init(b+":"+a)}})},!0),c?document.head.insertBefore(d,document.head.firstChild):document.body.appendChild(d)};document.head.setAttribute("data-senchainspectorport",a),d(c,!0)}();
```

* Start the Sencha Inspector 
* Click on the "Sencha Inspector" bookmark, a link to Feedviewer app should appear in the Sencha Inspector. 
* Click on the link and go to Theme tab to change Sass variables

### Create your Custom Theme

* Generate custom theme called “my-contest-theme”
In theming-workspace,
```
sencha generate theme my-contest-theme
```

* Extend “my-contest-theme” from "theme-triton". In the package.json file, change to "extend": "theme-triton"
```
{path/to/theming-workspace}/packages/local/my-contest-theme/package.json

"extend": "theme-triton",
```
* Use “my-contest-theme” in the feed viewer app
In the app.json file, change to "theme": "my-contest-theme". Optionally uncomment “save” to use Sencha Inspector changed Sass variables in save.json file. The resulting changes in app.json will look like
```
app.json

"builds": {
       "classic": {
           "toolkit": "classic",
           "theme": "my-contest-theme",
           "sass": {
               "save": "classic/sass/save.json"
           }
       },

       "modern": {
           "toolkit": "modern",
           "theme": "my-contest-theme",
           "sass": {
               "save": "modern/sass/save.json"
           }
       }
   }
```
* Copy changes from the Inspector (or save.json file) to custom theme. 
```
E.g. Add component variable $base-color: #639000; in
{path/to/theming-workspace}/packages/local/my-contest-theme/sass/var/Component.scss
```
* Create unique components with Ext JS UIs (CSS mixins).

### Submit your contest entry
Send us zipped file of your workspace containing your version of the Feed Viewer sample application as well as custom themes at contest@sencha.com. Please do not include ext directory in the zipped file.  All entries must be received by September 1, 2015.


### Resources
Watch our video to learn how to accelerate your theming efforts
* [ Getting Started with Themeing Contest Video ] (https://vimeo.com/133395706)
* [Docs - Theming in ExtJS] (http://docs.sencha.com/extjs/6.0/core_concepts/theming.html)

### Any Questions?
If you have any additional questions about the contest, please send those to contest forum at  [Sencha Contest Forum] (https://www.sencha.com/forum/forumdisplay.php?137-Sencha-Contests) 
