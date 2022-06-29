# Usage

For setup Outpost and Contextly integration

1. Copy folder `partials/integrations` to folder `partials` in your theme

2. Add code below in your theme `default.hbs` under {{ghost_foot}}

```
   {{> integrations/outpost domain="OUTPOST_DOMAIN_NAME" apiKey="OUTPOST_API_KEY"}}
   {{> integrations/contextly}}
```

Please do not forget to use valid Outpost domain and apiKey. You can find it in Outpost Control Center. 

3. Add Contextly module in needed place of your theme. Insert code below in `post.hbs` under {content} section
or in any needed place.

```
    {{> integrations/contextly-module}}
```
