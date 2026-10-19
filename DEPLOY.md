# Deploy SubsidySaathi

1. Create a new GitHub repository and upload all files from this folder to its root (including `render.yaml`). Do not upload `.env`, API keys, or local SQLite databases.
2. Sign into https://dashboard.render.com/ with GitHub.
3. Choose **New > Blueprint**, connect the repository, and apply `render.yaml`.
4. In Render, enter `OPENROUTER_API_KEY` and `TINYFISH_API_KEY` as secret environment variables if using those features. Never paste secrets into public GitHub files.
5. Wait for the deployment to finish. Render displays the live `https://...onrender.com` URL.

Note: Render's free filesystem is ephemeral. The SQLite demo database can reset on redeploy/restart, so this is not suitable for permanent tracking or storing real identity documents. Do not upload actual Aadhaar or other sensitive documents to this demo.
