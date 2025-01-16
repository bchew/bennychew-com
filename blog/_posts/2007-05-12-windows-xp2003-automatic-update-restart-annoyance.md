---
id: 175
title: Windows XP/2003 Automatic Update restart annoyance
date: 2007-05-12T20:31:29+00:00
author: Benny Chew
layout: post
guid: http://siansiew.com/2007/05/12/windows-xp2003-automatic-update-restart-annoyance/
permalink: /2007/05/12/windows-xp2003-automatic-update-restart-annoyance/
dpsp_networks_shares:
  - 'a:1:{s:11:"google-plus";i:0;}'
categories:
  - 'Tips &amp; Tweaks'
  - Windows
---
I got tired of my Windows 2003 automatic installation of security updates (and restart) when they are released, so I decided to go digging around to find a way to stop that. A quick Google search got me <a href="http://www.codinghorror.com/blog/archives/000294.html" target="_blank">this site</a>, whose step 2 did the trick. Here are the steps for my configuration:

  1. Go to Start->Run, and type &#8216;**gpedit.msc** &#8216; without the quotes and hit OK.
  2. Browse down to **Local Computer Policy**->**Computer Configuration**->**Administrative Templates**->**Windows Components**->**Windows Update**.
  3. The settings which I changed are: 
      * Enabled &#8216;**Configure Automatic Updates**&#8216; and set it to &#8216;3 &#8211; Auto download and notify for install&#8217;
      * Enabled &#8216;**No auto-restart for scheduled Automatic Updates installations**&#8216;
      * Disabled &#8216;**Allow Automatic Updates immediate installation**&#8216;
      * Enabled &#8216;**Re-prompt for restart with scheduled installations**&#8216; and set it to 1440 minutes

Screenshot of my Group Policy Object Editor:

[![Group Policy Object Editor - Windows Update](https://bennychew.com/blog/wp-content/uploads/2007/05/gpedit-windows-update.thumbnail.png)](https://bennychew.com/blog/wp-content/uploads/2007/05/gpedit-windows-update.png "Group Policy Object Editor - Windows Update")

As far as I know, Windows XP does not install updates automatically by default, so that might only be a default for Windows Server 2003 which I&#8217;m using. However, I believe the restart prompt is defaulted to 10mins for XP and 2003.