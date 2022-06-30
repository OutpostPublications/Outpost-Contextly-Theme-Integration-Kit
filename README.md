# Usage

To setup Outpost and Contextly integration, you will need to download your theme

1. Download the Outpost ThemeStarterKit files and unzip them.

2. Download your theme from Ghost and unzip it.

3. Copy the folder `partials/integrations` from the ThemeStarterKit to the folder `partials` in your theme.

4. Open the outpost_api_key.hbs file in a text editor. Go to your Outpost Control Center. In the top line, click Account -> Core Connections. Copy your Outpost API key and replace "Sample_Outpost_API_Key" in the outpost_api_key.hbs file. Make sure there is not any extra lines in the file. Then save the file.

5. Open the outpost_domain_name.hbs file in a text editor. Go to your Outpost Control Center. In the top line, click Account -> Core Connections. Copy your Outpost Domain Name and replace "example" in the outpost_domain_name.hbs file. Make sure there is not any extra lines in the file. Then save the file.

5. Add the following code into your theme's `default.hbs` file right under {{ghost_foot}}

```
   {{> integrations/outpost apiKey="OUTPOST_API_KEY"}}
   {{> integrations/contextly}}
``` 

6. Add the main Contextly module in the post file in your theme where you would like it to display, typically right after the end of the post and before the comments or author bio box. This file is typically called post.hbs. To place the module, paste the code below under the {content} section. 

If your theme has multiple post templates (like Biron Theme's Nikko theme), you will need to put this code in each post template you want it to appear in.

```
    {{> integrations/contextly-module}}
```

7. Zip all your theme files and then upload the zip file in Ghost as a new theme. Set it as active and you will be good to go.

If you run into any issues, please write us at support@outpost.pub.
