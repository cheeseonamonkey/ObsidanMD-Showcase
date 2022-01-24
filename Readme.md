# My Obsidan.MD Showcase

Cool stuff I've put together in [Obsidian.MD](https://obsidian.md).

Most of them are meta utilities, or just aim improve the user experience of the mobile Android app, which is still fairly new and is often unstable.

Some of them will have their own Readmes.



# Obsidian.MD:

### [**OrphanAdopter:**](/OrphanAdopter/)
Utility to help link connections between orphan files.
- very dynamic but a bit slow - it uses a lot of Javascript and has to query every single page in your vault
- requires **Dataview** plugin

### [**File management queries:**](/FileManagementQueries/)
Simple DataView queries but with advanced URI links. Generates links to *move* and *delete* without leaving the page at all. Used mainly for vault housekeeping and to manage newly-created files.

- very useful! those queried links are a *pain* to set up, but can be templated here for many other uses 
- requires both the **DataView** and **Advanced Obsidian URI** plugins 
- I actually wrote for Reddit once a tutorial on how to do this: [reddit post link](https://www.reddit.com/r/ObsidianMD/comments/rlljp9/dataview_queues_for_file_management_with_buttons/)




# **Obsidian Android App integrations:** *(MacroDroid)*

Most *(all?)* of these use [MacroDroid](https://play.google.com/store/apps/details?id=com.arlosoft.macrodroid&hl=en_US&gl=US), a powerful automation app available on the Play Store. The free version limited to 5 macros, and premium version is something around $6.


### [**QuickAppend:**](/QuickAppend/)
For me this is an insanely powerful feature, and really takes Obsidian's mobile app to the next level - I literally use 15+ times daily.

It allows you to append to an Obsidian file using an icon in your 'quick settings' tiles in the notification tray.  

I wrote a Reddit post that goes over this and other MacroDroid integrations: [reddit post link](https://www.reddit.com/r/ObsidianMD/comments/rkf22r/improving_the_obsidianmd_android_app_dramatically/)


### [**Hardware shortcuts:**](/AndroidHardwareShortcuts/)
Adds shortcuts to the Obsidian mobile app with hardware controls like volume keys, fingerprint scanner, and accelerometer.

I wrote a Reddit post that goes over this and other MacroDroid integrations: [reddit post link](https://www.reddit.com/r/ObsidianMD/comments/rkf22r/improving_the_obsidianmd_android_app_dramatically/)

### **[RandomSMSLogger](/RandomSMSLogger/)**

Anonymizes and logs 10% of all received SMS messages.


# Templater

### [Plugin Readmes](Templater/PluginReadmes/)

This may be a bit buggy but it is worth including, and it required manually (like in the OS) copying the JSON data for the plugins from the \.obsidian\ folder. You can fix up the code yourself and make a PR if you'd like :)

It creates a list of links to every plugin Readme. It is useful if you often need to reference plugin documentation (dataview/templater/etc.).

Requires the **Hotkey Helper** plugin to programmatically generate the Readme links.



### [PayStub template](Templater/PayStubTemplate/)

This isn't a big deal but I am including it just to demonstrate the underrated 'tp.prompt()' function.


# **Shell & cmd scripts**

Used to automate some vault management.

I used MacroDroid to run shell scripts on my phone, but results may vary with/without root privileges.

### [**Compress vault to tarball** *(shell)*:](/Bat-ShellScripts/)
Compresses vault to a tarball.

### [**Extract vault from tarball** *(cmd)*:](/Bat-ShellScripts/)
Creates vault from a compressed tarball.

