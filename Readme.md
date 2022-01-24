# My Obsidan.MD Showcase

Cool stuff I've put together in [Obsidian.MD](https://obsidian.md).

Most of them are meta utilities, or just aim improve the user experience of the mobile Android app, which is still fairly new and is often unstable.

Some of them will have their own Readmes.


- [Native Obsidian.MD](#obsidianmd)
- [Obsidian Android integrations](#obsidian-android-integrations-macrodroid)
- [Templater templates](#Templater)
- [Shell / cmd scripts](#shell--cmd-scripts)


# Obsidian.MD:

### [**OrphanAdopter**](/OrphanAdopter/)
Utility to help link connections between orphan files. Allows you to compile a bunch of page links directly into your clipboard with some post-processing.

It is very dynamic but can be slow - it uses a lot of Javascript and has to query every single page in your vault.

### [**File management queries**](/FileManagementQueries/)
Simple DataView queries but with advanced URI links. Very useful for vault housekeeping and to manage newly-created files.

Generates links to *move* and *delete* file, without leaving the current page at all. These queried links were a *pain* to set up, but can be easily templated from here for other uses too.



# **Obsidian Android integrations** *(MacroDroid)*

Most *(all?)* of these use [MacroDroid](https://play.google.com/store/apps/details?id=com.arlosoft.macrodroid&hl=en_US&gl=US), a powerful automation app available on the Play Store. The free version limited to 5 macros, and premium version is something around $6.


### [**QuickAppend:**](/QuickAppend/)
For me this is an incredibly powerful feature, and really takes Obsidian's mobile app to the next level. I literally use it 15+ times daily!

It allows you to append to an Obsidian file by pushing a custom button in your phone's 'quick settings' tiles in the notification tray. 

### [**Hardware shortcuts:**](/AndroidHardwareShortcuts/)
Adds shortcuts to the Obsidian mobile app with hardware controls like volume keys, fingerprint scanner, and accelerometer.

### **[RandomSMSLogger](/RandomSMSLogger/)**
Anonymizes and logs 10% of all received SMS messages.


# Templater

### [Plugin Readmes](Templater/PluginReadmes/)

This may be a bit buggy but it is worth including, and it required manually (like in the OS) copying the JSON data for the plugins from the \.obsidian\ folder. You can fix up the code yourself and make a PR if you'd like :)

It creates a list of links to every plugin Readme. It is useful if you often need to reference plugin documentation (dataview/templater/etc.).

Requires the **Hotkey Helper** plugin to programmatically generate the Readme links.


### [PayStub template](Templater/PayStubTemplate/)

This isn't a big deal but I am including it just to demonstrate the underrated 'tp.prompt()' function. It could be improved in many ways.


### [Misc templates](/Templater/Misc)

Other miscellaneous or short templates.


# **Shell & cmd scripts**

External from Obsidian. Used to automate some vault management.

I used MacroDroid to run shell scripts on my phone, but results may vary with/without root privileges.

### [**Compress vault to tarball** *(shell)*:](/Bat-ShellScripts/)
Compresses vault to a tarball.

### [**Extract vault from tarball** *(cmd)*:](/Bat-ShellScripts/)
Creates vault from a compressed tarball.

