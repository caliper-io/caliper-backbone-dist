# Caliper Backbone

### Bower Library

This repository is meant to be used with [bower](http://bower.io)
You should have bower installed already if you want to use this package.
These files are also available through the Caliper application dashboard.

### Getting Started

    $ bower install caliper-backbone


### Including Caliper in your App

Caliper extends Backbone to collect performance data as your users interact with
your application. This must be loaded after Backbone has been loaded, but before
any of your application's code are loaded.

If you are using any Backbone extensions, such as marionette.js, be sure to load
caliper.backbone.js before you load such extensions.

## Configuring your API Key

Include the following Javascript snippet to configure Caliper

    var Caliper = {
      config: { apiKey: "77e3433c-4a89-4e38-b8e2-f5d2df53abfc" }
    };


## Optional: Name your Backbone Views

To provide more context for your performance reports you can optionally assign a
\_\_name\_\_ attribute to your Backbone views. This attribute will be picked up 
by Caliper and displayed on your performance reports, so you will be able to 
easily pinpoint the source of any performance issues.

    // You can assign this attribute as you define your view:
    SCaliperIoApp.Views.NavbarView = Backbone.View.extend({
      __name__: "NavbarView",

      events: {
        'click': 'navItemClicked'
      },

      ...
    });

    // You can also assign the __name__ attribute after a view has been defined:
    SCaliperIoApp.Views.NavbarView.__name__ = "NavbarView";

    // This makes it very easy to name all your views in one go:
    for(var viewName in SCaliperIoApp.Views){
      SCaliperIoApp.Views[viewName].__name__ = viewName;
    }


