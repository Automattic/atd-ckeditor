atd-ckeditor
============   

## After the Deadline for CKEditor

[After the Deadline](http://www.afterthedeadline.com) is an [open source](http://open.afterthedeadline.com) software service that checks 
   [spelling, style, and grammar.](http://www.afterthedeadline.com/features.slp) This package contains an AtD CKEditor Plugin and instructions on how to
   use AtD with [CKEditor](http://ckeditor.com/).

Automattic no longer supports this plugin.  We're putting it on Github so that you can feel free to fork it, hack it, and release your own version.

### Installation

1.  Extract this archive into your ckeditor/plugins directory.
2.  You'll need to make up an API key. Ideally your application name followed by a string that is unique to this user is best. There is a performance benefit to using the same key for subsequent requests.
3.  Modify contents.css in your ckeditor/ directory and add the styles from atd.css to it.
4.  Modify config.js in your ckeditor/ directory (or where ever you're calling CKEditor from) to load the AtD plugin:

5.  As a final note, make sure your webpage is encoded in UTF-8 format. AJAX requests use the encoding of the parent website and AtD expects UTF-8. This is important as AtD supports accented characters and we're working to support more languages.

### Commercial use and running your own server

This plugin requires a running instance of an [After the Deadline Server](https://github.com/automattic/atd-server) in order to work.  Automattic operates an that you can use for personal use as long as you don't send too much traffic.  The extension is configured to use this instance by default.

For high volume and commercial uses of AtD, you must run your own server.  The code is available on Github: [After the Deadline Server](https://github.com/automattic/atd-server).  See the [After the Deadline Developer's page](http://open.afterthedeadline.com/) for more information, and check out the [AtD Developers Google Group](http://groups.google.com/group/atd-developers) for discussion and community support.  

When you run your own server, replace `service.afterthedeadline.com` with your server's hostname in _server/proxy.php_.

### Development Status

This plugin was developed as a proof-of-concept for the [AtD core UI module](https://github.com/automattic/atd-core). It lacks the polish of the other AtD plugins and needs a maintainer. Patches are very welcome.

Here is a list of things that need to be done:

*   Test and fix bugs with Internet Explorer (there may not be any for all I know)
*   Need to use something other than CKEditor Context Menu plugin for errors or fix CKEditor Context Menu. Here are the issues:

    *   Context menu is fixed width and doesn't resize for longer errors
    *   Context menu doesn't honor Ctrl+Click for single button mice
    *   Context menu uses cursor placement to determine which element the context menu was clicked on--makes using the menu awkward, user has to click the spelling error and then right click to bring up the context menu.
*   Need to find a way to get CKEditor to load AtD CSS on its own. I tried a few different ways, you may do better than I did.
*   Need to add "explain" menu for errors that have explanations
*   Should update plugin to use editor.config.atd_show_types and editor.config.atd_ignore_strings values to set preferences in Core UI Module

### Demo

A demo this extension is at: [http://www.polishmywriting.com/ckeditor/](http://www.polishmywriting.com/ckeditor/)

### Get Involved

### Contribute

We (Automattic) are no longer supporting this extension.  This code has always been open source.  We're putting it on Github so that you can feel free to fork it, hack it, and release your own version.

Join the [atd-developers](http://groups.google.com/group/atd-developers) list for support.

### License

LGPL
