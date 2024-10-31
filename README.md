# Usage

To setup the integration with Outpost and Contextly on your Ghost site, you will need to:
1) Sign up with Outpost and be moved by Outpost to a Luna+ plan [Outpost](https://admin.outpost.pub)
2) Sign up with Contextly for Ghost at https://ghost.contextly.com/login
3) Add your Contextly API key to Outpost's integrations to make it simpler to login (Contextly account page, copy the API key, go to Outpost then to Integrations, choose Contextly, paste the API key and hit Save. Then you can login to Contextly from Outpost).
4) Add a few files to your theme that activate both

This tutorial walks you through #3, the process of modifying your theme.

If you are not hosting your site on Github, you will need to download your theme.

Non-Github Method:

1. Download the Outpost ThemeStarterKit files and unzip them.

2. Download your theme from Ghost and unzip it.

3. Copy the folder `partials/integrations` from the ThemeStarterKit to the folder `partials` in your theme.

4. Open the outpost-api-key.hbs file in a text editor. Go to your [Outpost Control Center](https://admin.outpost.pub). Click the Account tab then go to Core Connections. Copy your Outpost API key. Go back to your text editor and replace "Sample_Outpost_API_Key" in the outpost-api-key.hbs file. Make sure there are no extra lines in the file. Then save the file.

5. Open the outpost-domain-name.hbs file in a text editor. Go to your [Outpost Control Center](https://admin.outpost.pub) again. Click the tab Account then Core Connections. Copy your Outpost Domain Name. Go back to your text editor and replace "example" in the outpost-domain-name.hbs file. Make sure there are no extra lines in the file. Then save the file.

6. Add the following code into your theme's `default.hbs` file right under {{ghost_foot}}

```
   {{> integrations/outpost}}
   {{> integrations/contextly}}
``` 

7. To display the main Contextly recommendation module at the end of posts, you need to add the main Contextly module in the post file in your theme where you would like it to display. This is typically right after the end of the post and before the comments or author bio box. This file is typically called post.hbs. To place the module, paste the code below under the {content} section and above the comments or author bio. 

If your theme has multiple post templates (like Biron Theme's Nikko theme), you will need to put this code in each post template you want it to appear in. These files generally start with "custom".

Alternatively, if your theme has a partial for this function e.g. related.hbs in the partials folder, you can comment out the existing code and paste the code below there instead.

```
    {{> integrations/contextly-module}}
```

8. Zip all your theme files (right-click on the folder and choose Compress). Now upload the zip file in Ghost as a new theme. Set it as active and you will be good to go.
9. If recommendations do not show up in 10 minutes, log into Contextly, go to Recommendations and Refresh all. If you copied over the Contextly API key into Outpost, you can login to Contextly via Outpost under Integrations.

Github method:

1. Open your theme in either your local Github editor or on the website.
2. Download the Outpost ThemeStarterKit files and unzip them.
3. Add these to your /partials folder. If doing this locally, copy the folder `partials/integrations` from the ThemeStarterKit to the folder `partials` in your theme.
4. Open the outpost_api_key.hbs file. Go to your <a href="https://admin.outpost.pub">Outpost Control Center</a>. Click the Account tab then go to Core Connections. Copy your Outpost API key. Replace "Sample_Outpost_API_Key" in the outpost_api_key.hbs file. Do this locally via a text editor, not via the online Github editor, which always adds a space somehow. Make sure there are no extra lines in the file. Then save your changes.
5. Open the outpost_domain_name.hbs file. Go to your <a href="https://admin.outpost.pub">Outpost Control Center</a>again. Click the tab Account then Core Connections. Copy your Outpost Domain Name. Replace "example" in the outpost_domain_name.hbs file. We also recommend doing this locally. Make sure there are no extra lines in the file. Then save your changes.
6. Add the following code into your theme's `default.hbs` file right under {{ghost_foot}}

```
   {{> integrations/outpost}}
   {{> integrations/contextly}}
``` 

7. To display the main Contextly recommendation module at the end of posts, you need to add the main Contextly module in the your theme's post or post files, where you would like it to display. This is typically right after the end of the post content and before the comments or author bio box. This file is typically called post.hbs. To place the module, paste the code below under the {content} section and above the comments or author bio. 

If your theme has multiple post templates (like Biron Theme's Nikko theme), you will need to put this code in each post template you want it to appear in. These files generally start with "custom".

Alternatively, if your theme has a partial for this function e.g. related.hbs in the partials folder, you can comment out the existing code and paste the code below there instead.

```
    {{> integrations/contextly-module}}
```
8. Commit your changes, open a pull request and approve them.
9. If you are using Actions to connect your theme to Ghost, check the Action tab to ensure the theme change was accepted by Ghost. If not using Actions, download your theme as a zip file, upload it to Ghost and make it active.
10. If recommendations do not show up in 10 minutes, log into Contextly, go to Recommendations and Refresh all.


If you run into any issues, please write us at support@outpost.pub.
