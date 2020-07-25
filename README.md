# NodeBB Discord OAuth2 SSO 

This plugin for [NodeBB](https://github.com/NodeBB/NodeBB/) provides a way to register/authenticate users against
[Discord](https://discordapp.com/). When enabled, and configured properly, there will be a
Discord icon available on the login screen. Click that icon to authenticate
against Discord.

## Using the Discord Logo:

I have included a modified version of the FontAwesome font that replaces the Discover card (fa-cc-discover) with a simplified Discord logo. I've picked Discover to overwrite because it starts with the same letters, so it's intuitive to search in the NodeBB icon box in case you want to use it elsewhere.

You'll have to patch this manually by replacing the font files in the fontawesome-discoverToDiscord folder with the ones in public/vendor/fontawesome.
I recommend keeping a copy of the folder itself in the font folder so that you can replace everything quickly everytime NodeBB upgrades, since they'll get overwritten with the default FontAwesome fonts.

If using the Discover card is unacceptable for you, you can do what I did and make your own version of the FontAwesome font using [FontForge](https://github.com/fontforge/fontforge). Just open up one of the base fonts, scroll to the icon you want to replace (they're buried deep), delete it and replace with the svg of your choice. Then export all of the filetypes and replace them in the fontawesome folder.

## Config

1. Create an application -- https://discordapp.com/developers/applications/me
2. Ensure the application's URI ends with `/auth/discord/callback`
3. Fill in the id and secret for the application via the NodeBB admin control panel (under "Social Authentication")

## Local Testing URL Override

I've added a setting in the admin panel that allows a workaround when testing local setups. Localhost isn't a valid OAuth URL, so to bypass this you can use [http://lvh.me](http://lvh.me), which will always resolve to 127.0.0.1. Just enter http://lvh.me:4567 (or whatever your port number is).

## Acknowledgements

This plugin is built from the one at [https://github.com/jsumners/nodebb-plugin-sso-discord-alt](https://github.com/jsumners/nodebb-plugin-sso-discord-alt).

## License

[MIT License](http://jsumners.mit-license.org/)