# WordPress Plugin Boilerplate with Namespace and Autoloader Support

This is a fork of the [WordPress Plugin Boilerplate](https://github.com/DevinVinson/WordPress-Plugin-Boilerplate) project and adds support for Namespaces and Autoloader. It requires PHP 5.6 and greater.

## Contents

The `wp-plugin-name` directory contains the source code - a fully executable WordPress plugin.

## Features

* The Boilerplate is based on the [Plugin API](http://codex.wordpress.org/Plugin_API), [Coding Standards](http://codex.wordpress.org/WordPress_Coding_Standards), and [Documentation Standards](https://make.wordpress.org/core/handbook/best-practices/inline-documentation-standards/php/).
* All classes, functions, and variables are documented so that you know what you need to change.
* The Boilerplate uses a strict file organization scheme that corresponds both to the WordPress Plugin Repository structure, and that makes it easy to organize the files that compose the plugin.
* The project includes a `.pot` file as a starting point for internationalization.

## Installation

The Boilerplate can be installed directly into your plugins folder "as-is". You will want to rename it and the classes inside of it to fit your needs.

* Copy wp-plugin-name to your plugin's directory and rename it to your plugin's name
* Perform a find and replace at the project level as follows:
  1. Find the text `wp-plugin-name` and replace with `your-plugin-name` in all files
  2. Find the text `WP_Plugin_Name` and replace with `Your_Plugin_Name` in all files
  3. Rename the `css` and `js` files under `inc\admin\css`, `inc\admin\js\`, `inc\views\js`, `inc\views\css` and replace the string `wp-plugin-name` with `your-plugin-name`
  4. Rename the `pot` file under `languages` and replace the string `wp-plugin-name` with `your-plugin-name`
  5. Find the text `http://example.com` and replace with your URI in all files
  6. Find the text `Your Name or Your Company` and replace with your name in all files
* Activate the plugin

#### Quick Commands to perform the Find and Replace #####
```	bash
# After having downloaded and extracted the archive, navigate to the folder containing the plugin
$ mv wp-plugin-name my-awesome-plugin
$ cd my-awesome-plugin
```
```	bash
# Replace text for "example.com/wp-plugin-name-uri" and "example.com"
$ grep -rl "example.com/wp-plugin-name-uri" ./* | xargs sed -i "s/example.com\/wp-plugin-name-uri/somedomain.com\/my-awesome-plugin-uri/g"

$ grep -rl "example.com" ./* | xargs sed -i "s/example.com/somedomain.com/g"
```
```	bash
# Replace text for "wp-plugin-name"
$ grep -rl "wp-plugin-name" ./* | xargs sed -i "s/wp-plugin-name/my-awesome-plugin/g"
```
```	bash
# Replace Namespace references for the text "WP_Plugin_Name"
$ grep -rl "WP_Plugin_Name" ./* | xargs sed -i "s/WP_Plugin_Name/My_Awesome_Plugin/g"
```
```	bash
# Rename Files with the text "wp-plugin-name" in them
$ find . -iname '*wp-plugin-name*' -exec rename 's/wp-plugin-name/my-awesome-plugin/' {} \;
```
```	bash
# Replace text for Your Name
$ grep -rl "Your Name or Your Company" ./* | xargs sed -i "s/Your Name or Your Company/Your Name/g"
```
Note that this will activate the source code of the Boilerplate, but because the Boilerplate has no real functionality there will be no menu items, meta boxes, or custom post types added.

### Plugin Structure

If you want to include your own classes, or third-party libraries

* `wp-plugin-name/inc/admin` - admin-specific functionality
* `wp-plugin-name/inc/core` - plugin core to register hooks, load files etc
* `wp-plugin-name/inc/frontend` - public-facing functionality
* `wp-plugin-name/inc/common` - functionality shared between the admin area and the public-facing parts
* `wp-plugin-name/inc/libraries` - libraries that the plugin may use

### PHP Version
Requires PHP `5.6.0` or greater

# Developer Notes

### The BoilerPlate uses a variable for the Text Domain

The WordPress Plugin Boilerplate uses a **variable** (`$this->plugin_text_domain`) to store the text domain, used when internationalizing strings. To take advantage of this method, there are tools that are recommended for providing correct, translatable files:

#### i18n Tools
* [Poedit](http://www.poedit.net/)
* [makepot](http://i18n.svn.wordpress.org/tools/trunk/)
* [i18n](https://github.com/grappler/i18n)

Any of the above tools should provide you with the proper tooling to internationalize the plugin. However, if you face problems translating the strings with an automated tool/process, replace `$this->plugin_text_domain` with the literal string of your plugin's text domain throughout the plugin.

### References:
* [Here's a discussion from the original project in favor of using variables](https://github.com/DevinVinson/WordPress-Plugin-Boilerplate/issues/59)
* [The Plugin Handbook Recommended Way (i.e. not to use variables)](https://developer.wordpress.org/plugins/internationalization/how-to-internationalize-your-plugin/#text-domains)

# License

The WordPress Plugin Boilerplate is licensed under the GPL v2 or later.

> This program is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License, version 2, as published by the Free Software Foundation.

> This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

> You should have received a copy of the GNU General Public License along with this program; if not, write to the Free Software Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA 02110-1301 USA

A copy of the license is included in the root of the plugin’s directory. The file is named `LICENSE`.

If you opt to use third-party code that is not compatible with v2, then you may need to switch to using code that is GPL v3 compatible.

For reference, [here's a discussion](http://make.wordpress.org/themes/2013/03/04/licensing-note-apache-and-gpl/) that covers the Apache 2.0 License used by [Bootstrap](http://twitter.github.io/bootstrap/).

# History

The original launch of this version of the boilerplate included the folder structure needed for using your plugin on WordPress.org. That folder structure has been moved to its own repo here: https://github.com/DevinVinson/Plugin-Directory-Boilerplate

# Credits

The WordPress Plugin Boilerplate was started in 2011 by [Tom McFarlin](http://twitter.com/tommcfarlin/) and has since included a number of great contributions. In March of 2015 the project was handed over by Tom to [Devin Vinson](https://github.com/DevinVinson/WordPress-Plugin-Boilerplate/)


# plugin-update-server
