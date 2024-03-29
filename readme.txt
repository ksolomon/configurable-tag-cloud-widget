=== Configurable Tag Cloud (CTC) ===
Contributors: zarathos
Tags: tags, tag cloud, widget
Requires at least: 2.8
Tested up to: 6.1.1
Stable tag: trunk

Display a tag cloud customized with your preferences in the sidebar.

== NOTE ==
Development on this plugin has STOPPED!  I am looking for someone to take it over.  Find more info [here](http://wp.me/p4xrG-7q)

== Description ==

The best new feature in WordPress 2.3 is the integration of tagging into the core of WordPress. However, the tag cloud widget & functions that are included leaves a lot to be desired. So, with time on my hands, I decided to whip up my own version of the tag cloud that lets you configure the tag cloud with all the customizations (well, almost, see below) the tag cloud template tag allows.

You can find the plugin home page (and leave comments) [here](http://keithsolomon.net/ctc/).

== Installation ==
1. Upload the `tag_cloud` folder to the `/wp-content/plugins/` directory.
2. Activate `Configurable Tag Cloud` through the 'Plugins' menu in WordPress.
3. Go to the `Widgets` control panel, and drag the `CTC` button into your sidebar list, and configure the options to your liking.  If you want to keep the defaults for the widget, just leave everything as-is (see FAQs for caveats).
4. (Optional) Add `ctc()` template tag to your theme.  Can be configured either via the Options menu, or via parameters in the template tag.

== Upgrade ==
I suggest using the built-in WordPress plugin update feature, but to manually upgrade, follow these instructions:
1. Deactivate the plugin in the WordPress admin menu.
2. Delete the existing `tag-cloud.php` file from the `/wp-content/plugins` folder.
3. Upload the `tag_cloud` folder to the `/wp-content/plugins/` directory.
4. Activate `Configurable Tag Cloud` through the 'Plugins' menu in WordPress and add the widget to your sidebar.
5. (Optional) Add `ctc()` template tag to your theme.  Can be configured either via the Options menu, or via parameters in the template tag.

== Changelog ==
You can always find the most up-to-date information about the plugin [here](http://keithsolomon.net/ctc/).

= 5.3 =
* Released 2023/03/29
* Fix: Added CSRF protection for the tag cloud options. Thanks to [(Abdi Pranata)](https://patchstack.com/database/researcher/92634a85-0e66-4059-aff6-1de1c49d0964) for pointing this out.
* Fix: Fixed php 8.1 compatibility issues.

= 5.2 =
* Released 2009/11/13
* Fix: Moved plugin files out of folder so WP Extend plugin update system can be used.
* Fix: Got rid of PHP short tags.
* Change: Added default class to cloud link elements.  Class name is "ctc-tag".  Thanks to Raafi Rivero [(desedo.com)](http://desedo.com) for bug report and link class suggestion.

= 5.1 =
* Released 2009/08/02
* Fix: Fixed issue with default options not being set on plugin activation.

= 5.0 =
* Released 2009/07/31
* Change: Modularized plugin to better handle troubleshooting issues.
* Change: Widget upgraded to new Widget API.  Retained backwards-compatibility with older versions of WordPress.
* Change: Widget is now fully multi-widget compliant.  You can now have multiple cloud widgets active with different settings for each.
* Change: Added support for limiting cloud by number of posts in each tag.  Both an upper and lower limit are supported.  Defaults for limits are 0 (lower) and 100 (upper).
* Change: Can now choose to not show tags (i.e., to show a category cloud).
* Change: Added "dropdown" cloud format.  Thanks to Scott Bradford of [Scott Bradford Creative Enterprises](http://www.scottbradford.us/) for the change.

= 4.5 =
* Released 2008/04/18
* Fix: Removed "Array" cloud format from widget control panel. More processing needs to be done to the array after creation in order to display, and you can't do that when using as a widget.  This was causing confusion, so it was removed.
* Fix: Removed limit for number of tags returned by default.  The plugin will now show ALL tags in your blog unless you specify a limit.
* Change: Added option menu for configuring the plugin when using the template tag.  Options set via the control panel can be over-ridden using parameters in the tag.  Widget and non-widget options are separate, giving you the ability to have multiple clouds with different options.

= 4.1 =
* Released 2008/02/22
* Fix: Fixed problem with category links not being made correctly.  Thanks to Robert Medlitsch for pointing it out.
* Change: Dropped the "Widget" from the name.  It no longer requires your theme to be widget-ready, so it was confusing.
* Change: Added new random sort feature for the cloud.  It will show a different randomly-sorted cloud each time your page is displayed.  Thanks to Chris for the suggestion.

= 4.0 =
* Released 2008/02/15
* Fix: Not assigning any colors in the widget control panel or the template tag will now make the cloud links use the defined CSS link color.  If only one color is supplied, your links will be that color.
* Change: Added support for categories in the cloud.  You can choose whether or not to show categories in the cloud, and whether to show empty categories.

= 3.2 =
* Released 2008/02/12
* Fix: Fixed problem with spaces after tags being underlined if using underline style for links in CSS and not using post counts.  Thanks to Eduard Roccatello pointing out the fix.

= 3.1 =
* Released 2008/02/06
* Change: Added support for "Array" format.  Thanks to Tim Einfeldt for request/testing.

= 3.0 =
* Released 2007/12/02
* Change: Added option to show post count after each tag. Thanks to Dovydas for the request.
* Change: Ability to use as a regular WordPress plugin. See below for PHP tag examples. Requested by too many people to mention here. Thank you all!

= 2.51 =
* Released 2007/10/19
* Fix: Fixed bug that prevented tag count options from working.  It came down to a bad variable name. Thank you to Paul & Joel for reporting the bug.

= 2.5 =
* Released 2007/10/16
* Fix: Fixed bug that would produce "Divide by zero" errors on display if you didn't input anything for smallest and/or largest font size in config form. Thanks to Ryan for uncovering this whopper.
* Change: Added div surrounding tag cloud for styling purposes. Thanks to everyone who suggested it.

= 2.0 =
* Released 2007/10/03
* Change: Added code necessary to enable coloring tag links by weight.
* Change: Stopped using WordPress-native tag cloud function in favor of internal widget function to generate tag cloud.
* Change: Removed "Array" format. I'm not sure it would be of any use running in a widget.
* Change: Added brief help text to the right of each field in the form.

= 1.0 =
* Released 2007/09/22
* Initial release of widget. Relied on WP tag cloud function to generate cloud.

Thanks to all who sent bug reports and ideas for improvements.
Please send me an email if I forgot to mention you here.

== Frequently Asked Questions ==

= Can I limit the tags that are shown in the cloud? =

(New in 5.0) YES! You can now choose to limit the tags shown in the cloud by the number of posts they are attached to.  For example, say you have one or two tags that are attached to 20 posts, but the rest only have one or two posts. Previously, these tags would be large, with the rest fairly small.  Now, you can tell the plugin that you want to exclude tags that have more than 10 posts, and those tags will be excluded from the cloud, with the rest following a (hopefully) smoother gradient in both color and size.  This also works for tags with fewer than a specified number of posts.

= Do I have to manually set parameters for the template tag? =

(New in 4.5) NO! I finally got around to adding an options page (located at `Settings->CTC`) for template tag usage.  Now using the template tag is as easy as adding `<?php ctc(); ?>` to your theme's template.  If you're using the array format, you'll still need to assign the function to an array and do post-processing (as mentioned in the example) to get it to work, but you can set all your options via the admin panel.  All options for the template tag are stored separately in the database from the options for the widget, so you could (for example) have one cloud using the widget in the sidebar and a second, completely different cloud in your footer by using the template tag.  You can also override any options set in the admin panel by using the respective parameters in the template tag call.

= Does the plugin work with categories? =

(New in 4.0) YES!  After many failed attempts to make this work, I finally figured it out.  By default, it doesn't display categories, but you can activate the option via the control panel, or using the `showcats` parameter for the template tag.  You can also choose whether or not to show empty categories in the cloud.  At present, there is no indication (other than the permalink) that a particular link in the cloud is a tag or a category.  (New in 5.0) You can now also choose to not show tags, thereby giving you the capability of showing a category cloud along with your tag cloud.

= Why are my tags black? =

(New in 4.0) Because they're set to black in your theme's stylesheet.  The function I'm using to generate the colors for the tag gradient used to return #000000 (black) if either (or both) of the color fields in the configuration form were left blank.  This has been fixed in 4.0.  Now, if you leave both fields blank, you get links in your cloud the same color as all other links in your page or sidebar (depending on how you have your links set up in your stylesheet).  If you leave one or the other blank (i.e., you set a minimum color, but not a maximum, or vice versa), you get links of that color.

= Will this work without widgets support? =

(New in 3.0) YES!  The function for the most part uses the same format as the stock WordPress tag cloud function, with some notable additions.  Listed below are the arguments and defaults for the `ctc()` function.  Note that when using the template tag, you need to specify the title manually.  The function uses the standard query string format for arguments.

    ARGUMENT                       FUNCTION                      DEFAULT VALUE
    --------------------------------------------------------------------------
    smallest=#                     Smallest font size to use     8
    largest=#                      Largest font size to use      22
    unit=pt|em|%|px                Unit for font size            pt
    minnum=#                       Minimum number of posts for   0
                                   a tag or category to show
                                   in the cloud
    maxnum=#                       Maximum number of posts for   100
                                   a tag or category to show
                                   in the cloud
    mincolor=#xxxxxx               Low color for gradient        none
    maxcolor=#xxxxxx               High color for gradient       none
    format=flat|list|array|drop    Format for tag cloud          flat
    number=#                       Number of tags to show        all
    orderby=name|count|rand        Sort field for tags           name
    order=ASC|DESC                 Order of cloud                ASC
    showcount=yes|no               Show post count after tags    no
    showcats=yes|no                Show categories in the cloud  no
    showtags=yes|no                Show tags in the cloud        yes
    empty=yes|no                   Show empty categories         no

= EXAMPLES =
= Basic template tag: =
    `<?php ctc(); ?>`

This would display a cloud using the options set in the admin panel, or the defaults if no options have been set.

= Template tag with parameters: =
    `<?php ctc('smallest=10&largest=18&unit=px&mincolor=#c0c0c0&maxcolor=#000000&showcount=yes&minnum=2&maxnum=10'); ?>`

This would show a cloud with all tags that have at least 2 posts and no more than 10 posts displayed, font size from 10 to 18 pixels, a color gradient of #c0c0c0 to #000000, and post counts after each tag.

= Array Example: =
    `<?php
        $tags = ctc('format=array&smallest=10&largest=18&unit=px&mincolor=#c0c0c0&maxcolor=#000000&showcount=yes&minnum=2&maxnum=10');

        foreach ($tags as $tag) {
            echo $tag."\n";
        }
    ?>`

This would give you the same output as the second example, but output to the page using an array.

== Screenshots ==
1. Widget Configuration Form
2. Template Tag Configuration Form
3. Sample Output ("Site Tags" as title, color gradient from #217ece to #003663, font gradient from .875em-1.15em, post counts shown, categories shown, empty categories shown, sorted by name ascending)
