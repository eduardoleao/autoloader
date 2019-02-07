# Autoloader

Enables standard WordPress plugins contained in a directory to be placed in the mu-plugins directory and loaded prior to others (forked from Bedrock).

* [Plugin Homepage (LittleBizzy.com)](https://www.littlebizzy.com/plugins/autoloader)
* [Free Facebook Group](https://www.facebook.com/groups/littlebizzy/)

### Defined Constants

    /* Plugin Meta */
    define('DISABLE_NAG_NOTICES', true);

### Compatibility

This plugin has been designed for use on [SlickStack](https://slickstack.io) web servers with PHP 7.2 and MySQL 5.7 to achieve best performance. All of our plugins are meant for single site WordPress installations only — for both performance and usability reasons, we strongly recommend avoiding WordPress Multisite for the vast majority of your projects.

Any of our WordPress plugins may also be loaded as "Must-Use" plugins (meaning that they load first, and cannot be deactivated) by using our free [Autoloader](https://github.com/littlebizzy/autoloader) script in the `mu-plugins` directory.

### Support Issues

Please do not submit Pull Requests. Instead, kindly create a new Issue with relevant information if you are an experienced developer, otherwise you may become a [**LittleBizzy.com Member**](https://www.littlebizzy.com/members) if your company requires official support.

----

## Changelog

= 1.1.0 =

* tested with PHP 7.0
* tested with PHP 7.1
* tested with PHP 7.2
* re-written with new PHP namespaces
* changed wp_options name to `littlebizzy_autoloader`
* optimized plugin code (e.g. prevent direct calls, minify wp_options data, etc)
* improved "duplicate queries" issue:

Effectively when the local plugin option cache is empty (or it is added or removed a mu-plugin directory), there is a double call to the updateCache method that duplicates the query (originated from the pluginsCount method)... There is only one scenario when this double call is made on purpose: the must-use plugins screen, where calls the updatecache method to retrieve all plugins info to show the autoloaded plugins list.

= 1.0.0 =

* forked from [Bedrock](https://github.com/roots/bedrock/blob/master/web/app/mu-plugins/bedrock-autoloader.php)
* tweaked plugin meta
