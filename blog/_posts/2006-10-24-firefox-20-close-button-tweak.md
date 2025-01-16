---
id: 119
title: Firefox 2.0 close button tweak
date: 2006-10-24T10:45:16+00:00
author: Benny Chew
layout: post
guid: http://siansiew.com/2006/10/24/firefox-20-close-button-tweak/
permalink: /2006/10/24/firefox-20-close-button-tweak/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:0;}'
categories:
  - Firefox
  - Open Source
  - 'Tips &amp; Tweaks'
  - Web
---
<a target="_blank" href="http://www.mozilla.com/firefox/"><img align="left" title="Mozilla Firefox" alt="Mozilla Firefox" src="https://bennychew.com/blog/wp-content/uploads/2006/09/firefox-logo-64x64.png" /></a>One of the more obvious user interface changes in this version of <a target="_blank" href="http://www.mozilla.com/firefox/">Firefox</a> is the position of the close button for tabs. Practically all other web browsers with tabs have tab closing buttons on each tab as opposed to Firefox&#8217;s choice of having it at the extreme right of the tab row up until now. With version 2.0, the default close tab button position is now on each individual tab.

This is probably a good decision in a way, but after such a long time of using Firefox, I&#8217;ve been too accustomed to the close button being there and would rather not have that change (I use the scroll button to close tabs nowadays, but selectively closing multiple tabs with the &#8216;x&#8217; at the end is pretty useful). Fortunately there&#8217;s a setting which can be easily changed to accommodate the behaviour you want.

Here are the steps to have the close button back at same position as pre-1.5 days:

>   1. Type &#8216;about:config&#8217; in the address bar.
>   2. In the filter textbox that appears below, enter &#8216;browser.tabs.closeButtons&#8217;.
>   3. Double click on the browser.tabs.closeButtons preference, and a message box should appear.
>   4. Change the value to &#8216;3&#8217; and click OK.

And you&#8217;re back with the close button at the same position as before the latest upgrade! You can easily revert to the default Firefox 2.0 behaviour by changing the value back to 1.

Default:

<img alt="Firefox 2.0 default close tab behaviour" id="image124" src="https://bennychew.com/blog/wp-content/uploads/2006/10/ff2-tab-before.png" />

After change of value:

<img alt="Firefox 2.0 modified close tab behaviour" id="image123" src="https://bennychew.com/blog/wp-content/uploads/2006/10/ff2-tab-after.png" />

Here are some other values you could use for that preference:

>   * 0 &#8211; Display a close button on the active tab only
>   * 1 &#8211; Display close buttons on all tabs (Default)
>   * 2 &#8211; Donâ€™t display any close buttons
>   * 3 &#8211; Display a single close button at the end of the tab strip (Firefox 1.x behavior)

_<a target="_blank" href="http://kb.mozillazine.org/Browser.tabs.closeButtons">browser.tabs.closeButtons</a> values and explanations taken from <a target="_blank" href="http://kb.mozillazine.org/">MozillaZine Knowledge Base</a>._