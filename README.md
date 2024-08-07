# Fantastic Microsoft Edge Annoyances and Where to Disable Them
I needed to use Edge for something recently and was annoyed at the sheer volume of worthless junk settings that are enabled by default. I figured I'd chronicle all the stuff I disabled for reference.

If you are forced to use Edge over Firefox, I hope you find the following modest list of annoying default settings helpful. Almost all of these should be turned off if you value privacy, security, and a browser that performs the sole purpose of browsing without any other [nonsense](https://thomask.sdf.org/blog/2023/03/18/the-dark-defaults-of-microsoft-edge.html).

#### It is worth nothing that I omitted a select few settings that some may wish to disable. Please be aware of this and make any adjustments in accordance with your own personal preferences.

## Last updated 2024-07-16, Version 126.0.2592.102 (Official build) (64-bit)

### Validated on Windows. Untested on Linux/macOS/mobile operating systems.

### If I missed anything, let me know in an Issue!

## Settings

### Profiles
* Profile Settings
    * Sync
        * Turn off sync [Important: It seems that sync may get re-enabled without your consent so you will need to continually check it]
    * Microsoft Rewards
        * Turn off "Earn Microsoft Rewards in Microsoft Edge"
    * Profile preferences
        * Uncheck "Allow single sign-on for work or school sites using this profile"
    * Share Browsing Data with other Windows Features
        * Uncheck "Share browsing data with other Windows features"
    * Microsoft Wallet -> Settings
        * Payment methods
            * Uncheck "Save and fill basic info"
            * Uncheck "Show Buy now, pay later option on sites when you shop"
            * Uncheck "Show Express checkout on sites when you shop"
        * Order tracking
            * Uncheck "Track your oder status"
        * Personal Info
            * Uncheck "save and fill custom info"
            * Uncheck "Automatically fill my info on sign up forms"
        * Memberships
            * Uncheck "Save and fill memberships"
        * Tickets
            * Uncheck "Display your travel reservation data from Bing"
        * Donation
            * Uncheck "Show opportunities to support causes and nonprofits you care about"
        * E-tree
            * Uncheck "Show E-tree in Wallet"
* Privacy, search, and services
    * Privacy
        * Uncheck "Allow sites to check if you have payment methods saved"
    * Services
        * You can effectively disable everything here, this is all junk like coupons, Shopping, nonprofit stuff, etc.
	    * Disable "Use a web service to help resolve navigation errors"
	    * Disable "Suggest similar sites when a website can't be found"
	    * Disable "Save time and money with Shopping in Microsoft Edge"
	    * Disable "Get notifications of related things you can explore with Discover"
	    * Address bar and search -> Search engine used in the address bar = DuckDuckGo
    * Search and service improvement
        * Uncheck "Help improve Microsoft products by sending the results from searches on the web"
	* Personalize your web experience
        * Uncheck "Improve your web experience by allowing Microsoft to use your browsing history from this account for personalizing advertising, search, news and other Microsoft services"
        * Address bar and search
            * Uncheck "Show me search and site suggestions using my typed characters"
* Start, home, and new tabs
    * New tab page
        * Uncheck "Preload the new tab page for a faster experience"
* Default browser
	* Internet Explorer compatibility
		* Let Internet Explorer open sites in Microsoft Edge -> "Incompatible sites only"
        * Allow sites to be reloaded in Internet Explorer mode -> "Allow"
* Languages
	* Uncheck "Use writing assistance"
* System and performance
	* System
        * Uncheck "Startup boost"
	* Uncheck "Continue running background extensions and apps when Microsoft Edge is closed"
	* Optimize Performance
	* Uncheck "Improve your PC gaming experience with efficiency mode"
* General Misc
	* Hide the right-hand sidebar with CTRL + Shift / or by going to the "..." menu and selecting "hide sidebar"
* Sidebar
    * Uncheck "Always show sidebar"
    * Uncheck "personalize my top sites in customize sidebar"
    * Uncheck "allow sidebar apps to show notifications"
    * Uncheck Copilot
* Languages
    * Uncheck "Collaborate with Copilot as you write on the web"
    * Uncheck "Use text prediction"
* New Tab page
    * At the "new tab" page, click the settings cog in the upper right and uncheck "show promoted links, "show greeting" and "new tab tips" as well as set "content" to "content off."
* Get rid of the Bing button:
    * [If on the newest Edge](https://www.thurrott.com/cloud/web-browsers/microsoft-edge/281051/microsoft-now-lets-you-hide-the-bing-button-in-edge):
        * Settings -> Sidebar > App and notification settings > Discover -> Toggle off "Show Discover."
    * [If on older versions of Edge that have the button](https://techdows.com/2023/03/disable-or-remove-bing-button-microsoft-edge.html):
        * Close Edge
        * Use these PowerShell commands to create the key (run PowerShell as administrator):
            * If you want to make this mandatory (cannot change setting without reg key removal):
                * ``New-Item -Path "HKLM:\SOFTWARE\Policies\Microsoft\Edge" -type Directory``
                * ``New-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Edge" -Name "HubsSidebarEnabled" -Value 0 -PropertyType Dword -Force``
                * If you left Edge open during this, visit ``edge://policy``, and click reload policies.
                * A side-effect of this is you will get a "managed by your organization" notice in the Edge menu. This can be ignored.
            * If you want to make this an default-but-revertable setting:
                * ``New-Item -Path "HKLM:\SOFTWARE\Policies\Microsoft\Edge\Recommended" -type Directory``
                * ``New-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Edge\Recommended" -Name "HubsSidebarEnabled" -Value 0 -PropertyType Dword -Force``
* Disable first run experience:
    * Use these PowerShell commands to create the key (run PowerShell as administrator):
        * ``New-Item -Path "HKLM:\SOFTWARE\Policies\Microsoft\Edge" -type Directory``
        * ``New-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Edge" -Name "HideFirstRunExperience" -Value 1 -PropertyType Dword -Force``
* Disable default browser prompt:
    * Use these PowerShell commands to create the key (run PowerShell as administrator):
        * ``New-Item -Path "HKLM:\SOFTWARE\Policies\Microsoft\Edge" -type Directory``
        * ``New-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Edge" -Name "DefaultBrowserSettingEnabled" -Value 0 -PropertyType Dword -Force``
* Set home page to blank:
    * Use these PowerShell commands to create the key (run PowerShell as administrator):
        * ``New-Item -Path "HKLM:\SOFTWARE\Policies\Microsoft\Edge\Recommended" -type Directory``
        * ``New-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Edge\Recommended" -Name "HomepageLocation" -Value "about:blank" -PropertyType String -Force``
* Set new tab page to blank:
    * Use these PowerShell commands to create the key (run PowerShell as administrator):
        * ``New-Item -Path "HKLM:\SOFTWARE\Policies\Microsoft\Edge\Recommended" -type Directory``
        * ``New-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Edge\Recommended" -Name "NewTabPageLocation" -Value "about:blank" -PropertyType String -Force``

Check out [Hope This Helps](https://hthpc.com/) if you liked this!
