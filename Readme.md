# My Obsidan.MD Showcase

Cool stuff I've put together in [Obsidian.MD](https://obsidian.md).

Most of them are meta utilities, or aim to improve the user experience of the mobile Android app.

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




# [**Obsidian Android integrations:**]() *(MacroDroid)*

Most *(all?)* of these need use [MacroDroid](https://play.google.com/store/apps/details?id=com.arlosoft.macrodroid&hl=en_US&gl=US), a powerful automation app available on the Play Store. The free version limited to 5 macros, and premium version is something around $6.


### [**QuickAppend:**]()
For me this is an insanely powerful feature, and really takes Obsidian's mobile app to the next level - I literally use 15+ times daily.

It allows you to append to an Obsidian file using an icon in your 'quick settings' tiles in the notification tray.  

I wrote a Reddit post that goes over this and other MacroDroid integrations: [reddit post link](https://www.reddit.com/r/ObsidianMD/comments/rkf22r/improving_the_obsidianmd_android_app_dramatically/)


### [**Hardware shortcuts:**]()
Adds shortcuts to the Obsidian mobile app with hardware controls like volume keys, fingerprint scanner, and accelerometer.

I wrote a Reddit post that goes over this and other MacroDroid integrations: [reddit post link](https://www.reddit.com/r/ObsidianMD/comments/rkf22r/improving_the_obsidianmd_android_app_dramatically/)


# [**Shell/cmd scripts**]()

Used to automate some vault management.

I used MacroDroid to run shell scripts on my phone, but results *may* vary with/without root privileges.

### [**Compress vault to tarball** *(shell)*:]()
Compresses vault to a compressed tarball.

### [**Extract vault from tarball** *(cmd)*:]()
Creates vault folder from a compressed tarball.
