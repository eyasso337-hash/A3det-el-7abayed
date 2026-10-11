A3det el 7abayed — free-hosting-ready Discord login project

This project is configured for a free Render web service (subject to Render's current free-plan limits). It cannot be published automatically from this chat; you must connect your own GitHub/Render accounts and enter Discord credentials privately.

Deploy overview:
1) Upload this folder to a GitHub repository (keep it private if preferred).
2) In Render, create a new Blueprint and connect that repository. Render will read render.yaml.
3) In Discord Developer Portal (https://discord.com/developers/applications), create an application, copy Application ID and create a Client Secret. Add a bot and invite it to your server. Never share the secret or bot token.
4) Once Render creates the service, copy its HTTPS URL, e.g. https://YOUR-SERVICE.onrender.com.
5) In Render environment variables set DISCORD_CLIENT_ID, DISCORD_CLIENT_SECRET, DISCORD_BOT_TOKEN, and DISCORD_REDIRECT_URI=https://YOUR-SERVICE.onrender.com/auth/callback. DISCORD_GUILD_ID is already configured as 1516430610678157412.
6) In Discord Developer Portal > OAuth2 > Redirects, add that exact redirect URI and save.
7) Ensure the bot is in your server. The backend uses the bot token only server-side to check membership and resolve role names.
8) Redeploy, open the public site, and test Discord login.

Notes:
- The website uses OAuth2 identify; it does not ask for a Discord password.
- Do not put Client Secret or Bot Token in index.html, screenshots, or chat. Enter them only in Render's private environment settings.
- If the bot cannot access the guild member endpoint, membership/roles may not appear.
- Render free services may sleep when idle and may have usage limitations.
- Live server member count requires Discord Server Widget to be enabled and is separate from OAuth login.
