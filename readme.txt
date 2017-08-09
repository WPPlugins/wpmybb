=== Plugin Name ===
Contributors: MonochromeNight
Donate link:
Tags: bridge, mybb
Requires at least: 2.0.2
Tested up to: 2.2.2
Stable tag: 0.5

This is a bridge between WordPress blogging platform and MyBB message board.
They can be found at http://wordpress.org and http://www.mybboard.net.

== Description ==

<b>How this works</b>
WP/MyBB is composed of two plugins: a WordPress plugin that acts as the "WP side" of WP/MyBB, and a MyBB plugin that acts as the "MyBB side".
When the WP side is active, WP/MyBB will create a MyBB thread for each WP post in the specified forum section.
The posts of that thread will act as the WP post comments.
You can also choose to display those MyBB posts just as if they were WP comments; in this case a "Comment post on the forums" link will be added. Otherwise the "Comments" link under a WP post will link directly to the corresponding thread.
Editing or deleting the WP post will result in changing or deleting the corresponding thread.
When the MyBB side is active, creating, editing or deleting threads in the specified forum section will result in adding, changing or deleting WP posts. 

<b>Why you need this</b>
Just think of a "News" section in your message board with all the threads displayed as post entries on your WordPress site.
WP/MyBB can also be useful if you want to let your user write news for your site: writing news on the forum, they will appear on your WordPress site automatically.

== Installation ==

Since this is a Pre-Alpha version, I encourage you to make vanilla WordPress and MyBB installs to test the plugin on your server first, without screwing up your website and message board.

<strong>WP side</strong>
To install WP/MyBB just extract the "wp" files in your WordPress folder and the "mybb" files in your MyBB folder.
Then just activate the WP plugin from your WP admin section and configure it going to Plugins -> WP/MyBB Configuration.
You can use the following WP/MyBB functions in your theme:
- wpmybb_get_thread_link()
- wpmybb_comments_popup_link($line)
wpmybb_get_thread_link() returns the URL of the corresponding thread of the current post (if it has one) in the WordPress Loop.
wpmybb_comments_popup_link() is the same as wp_comments_popup_link, except that it will show a link to the corresponding thread instead of the WP comments link if Comments on WP is set to false in WP/MyBB Configuration. Plus it will display the username of the last poster in that thread. Just replace wp_comments_popup_link with wpmybb_comments_popup_link in your theme, and you're done.
You can customize the "Last comment by $user" line passing a string to wpmybb_comments_popup_link(). The $user tag will be replaced with the username of the last poster.
Example: wpmybb_comments_popup_link("Last post by $user");
You should also delete from your theme the HTML code that displays the "Leave a reply" box, since the WP comments system won't work.

<strong>MyBB side</strong>
If you want that adding, editing or deleting MyBB posts in the specified forum section will result in adding, changing or deleting WP posts, you have to activate the MyBB plugin and configure it from the Admin section of your message board.

== Frequently Asked Questions ==

= I need X function, when will you add it? =

Other functions will be added in the future, such as a "Welcome block" integration and other stuff.
You can read the roadmap and follow the development stages on http://www.wehaveexplosive.com/page.php?id=7 .
Anyway, if you want to request a particular feature you don't see in the roadmap, you can contact me at hangman@ordinaryvanity.com .