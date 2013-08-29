atd-core
========

### After the Deadline Core UI Module - README

[After the Deadline](http://www.afterthedeadline.com) is an [open source](http://open.afterthedeadline.com/) software service that [checks spelling, style, and grammar](http://www.afterthedeadline.com/features.slp).

This package contains an adaptable JavaScript object to make it easier to add After the Deadline to other WYSIWYG editors and libraries.

This package includes logic to parse the AtD XML protocol, walk a DOM structure and highlight errors, remove highlighted errors, and locate error metadata and suggestions given a highlighted element. If you intend to use AtD beyond the maintained front-end plugins, this extension will save you time.

Automattic no longer supports this module.  We're putting it on Github so that you can feel free to fork it, hack it, and release your own version.

### Using the Module

To use this module, you must instantiate it and then add several functions to the module to tell it how to perform certain actions in your environment. To instantiate this module:

The functions that you must define are:

You are responsible for adding the contents of the _atd.css_ stylesheet to your application or library. These styles tell your browser how to display the AtD markup to your user.

Once you load the stylesheet and provide implementations of these functions to the module, then you can use the Core UI API.

### Core UI API

### Development Tips

Here are some tips I've learned the hard way:

1.  Wrap your functions that call this API in a try/catch block and make sure you're notified when an exception occurs. Some libraries *cough*CKEditor*cough* think its a good idea to swallow all uncaught exceptions. By wrapping your code in a try/catch block you'll be able to handle uncaught exceptions by notifying yourself.
2.  Use Firebug and console.log() to show you what the methods you defined for the core UI module are receiving and returning. If any of these functions fails to work as expected then the core UI module will break in mysterious ways.

### Examples

There are several plugins/libraries that use this module, for example:

*   [AtD/jQuery](http://github.com/automattic/atd-jquery)
*   [AtD/TinyMCE](http://github.com/automattic/atd-tinymce)

### Localization

To localize the strings in this extension, create an object with the localized strings. Here is an example:

<pre>var my_plugin_strings = {
   menu_title_spelling: "Spelling",
   menu_title_repeated_word: "Repeated  Word",
};</pre>

Then make AtD use these strings:

   <pre>core.addI18n(my_plugin_strings);</pre>

Optionally, you can redefine the `core.getLang("key", "default")` function to hook into your libraries localization function. This module
   uses the _menu_title_spelling_ and _menu_title_repeated_word_ keys.

### License

Unless otherwise noted, the resources here are licensed under [LGPL](http://www.opensource.org/licenses/lgpl-2.1.php).

### Contact

We (Automattic) are no longer supporting this library.  This code has always been open source.  We're putting it on Github so that you can feel free to fork it, hack it, and release your own version.

Join the [atd-developers](http://groups.google.com/group/atd-developers) list for support.
