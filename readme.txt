=== WP MVC ===
Contributors: tombenner
Tags: mvc, framework, model, view, controller, development, plugin
Requires at least: 3.0
Tested up to: 3.2.1
Stable tag: 1.1.1

WP MVC is a full-fledged MVC framework, similar to CakePHP and Rails, that developers can use to create WordPress plugins.

== Description ==

WP MVC is a WordPress plugin that allows developers to use a MVC framework to create plugins. It is a full-fledged framework with architecture that's similar to that of CakePHP or Ruby on Rails. Developers can consequently use it to rapidly build sites that take advantage of both WordPress's large native functionality and all of the many advantages of an MVC framework. 

WordPress supports a number of specific content types natively, but setting up custom post types and all of the necessary related functionality (public views, administrative management, associations, etc) is typically more time-consuming than doing the equivalent work in an MVC framework. The resulting code and database structure is significantly less graceful than the MVC equivalent, too.

WP MVC fills this gap. The basic idea is that you create an app/ directory that contains a file structure similar to other MVC frameworks (controllers/, helpers/, models/, views/, etc) and set up models, views, and controllers just as you would in other frameworks. WP MVC runs this code in the context of WordPress (i.e. you can still use all of WordPress's functionality inside of app/). Since WordPress already provides an administrative system, admin actions and views in app/ are run in that context, with WP MVC adding all of the necessary WordPress actions and filters to make this possible without the developer needing to lift a finger. An [Administration Menu](http://codex.wordpress.org/Administration_Menus) is automatically created for each model, but it can be customized or omitted.

For more extensive documentation, and to see what WP MVC is capable of, please visit [wpmvc.org](http://wpmvc.org).

If you'd like to grab development releases, see what new features are being added, or browse the source code please visit the [GitHub repo](http://github.com/tombenner/wp-mvc).

== Installation ==

1. Put `wp-mvc` into the `wp-content/plugins` directory
1. Activate the plugin in the "Plugins" menu in WordPress
1. Make sure that [Pretty Permalinks](http://codex.wordpress.org/Introduction_to_Blogging#Pretty_Permalinks) are enabled and working
1. Either set up one of the example plugins to see how WP MVC works or start creating a plugin using the code generation utility `wpmvc`:

#### Setting up one of the example WP MVC-based plugins:

1. Copy its directory (e.g. `wp-content/plugins/wp-mvc/examples/events-calendar-example`) into the `wp-content/plugins` directory (e.g. `wp-content/plugins/events-calendar-example`)
1. Activate the plugin in the "Plugins" menu in WordPress

After doing so, you should see administrative menus for each model in WordPress, and you'll be able to browse to URLs like `/events/`, `/events/1/`, `/venues/`, etc to see the public-facing views.

#### Creating a WP MVC-based plugin

It only takes four simple steps to create a basic WP MVC-based plugin:

1. Create the initial plugin code using a single command (WP MVC provides a code generation utility)
1. Write the SQL to create any tables that the plugin uses
1. Create the initial code for the models, views, and controllers using a single command for each resource
1. Modify the generated models, views, and controllers to customize the app

For a simple example tutorial on this, please see the [tutorial on wpmvc.org](http://wpmvc.org/documentation/70/tutorial/).

== Frequently Asked Questions ==

= What relation does this have to other MVC frameworks? =

WP MVC is a full-fledged MVC framework, but behind the scenes it uses existing WordPress functionality to lessen its footprint and better interface with the parent WordPress application. The developer will not need to know about much of this, though, and may merely treat it as another MVC framework. It draws on concepts and workflows from other MVC frameworks; Rails and CakePHP are the biggest influences, and you may see some of their naming conventions being used.

= Is feature X available? =

Most of the functionality that's available is used in the example plugins, so if there's functionality that you'd like to use that isn't implemented in those or mentioned on [wpmvc.org](http://wpmvc.org), it may not exist yet. However, if it's something that is widely useful, I'd certainly be willing to implement it myself or to accept any well-written code that implements it. Please feel free to either add a topic in the WordPress forum or contact me through GitHub for any such requests:

* [WordPress Forum](http://wordpress.org/tags/wp-mvc?forum_id=10)
* [GitHub](http://github.com/tombenner/)

== Screenshots ==

1. If you've worked with MVC frameworks before, the file structure for WP MVC will look refreshingly familiar.
2. Administration Menus are added automatically for each model, but they can be customized or omitted.
3. An example of the default "admin/index" view, which includes search functionality and pagination by default and can be customized.
4. An example of the default "admin/add" view. See the next screenshot for the code that creates it.
5. The code of the "admin/add" view in the previous screenshot. Forms can be easily created using the form helper, which includes an `input()` method that automatically determines the data type of the field and shows an appropriate input tag. Methods for most types of inputs (textareas, hidden inputs, select tags, checkboxes, etc) are also available, as are association-related input methods like `belongs_to_dropdown()` and `has_many_dropdown()`.