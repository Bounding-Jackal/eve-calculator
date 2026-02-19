# EVE Capital Construction Calculator

Live build cost estimator with ESI integration for assets, industry jobs, and PI colonies.

## Deployment (GitHub Pages)

### 1. Push these files to your repo

Your repo should look like this:
```
eve-calculator/
├── index.html          ← main app
└── callback/
    └── index.html      ← OAuth2 callback handler
```

### 2. Enable GitHub Pages

1. Go to your repo on GitHub → **Settings** → **Pages**
2. Under **Source**, select **Deploy from a branch**
3. Choose **main** branch, **/ (root)** folder
4. Click **Save**

Your app will be live at:
`https://bounding-jackal.github.io/eve-calculator/`

### 3. Configure your ESI application

1. Go to https://developers.eveonline.com
2. Find your application → **Edit**
3. Make sure the **Callback URL** is set to:
   `https://bounding-jackal.github.io/eve-calculator/callback`
4. Make sure these scopes are enabled:
   - `esi-assets.read_assets.v1`
   - `esi-industry.read_character_jobs.v1`
   - `esi-planets.manage_planets.v1`
5. Save

### 4. Use it

Visit `https://bounding-jackal.github.io/eve-calculator/`, click **LOGIN WITH EVE**,
approve the scopes, and you'll be redirected back with your character data loaded.

## Notes

- Tokens are stored in `sessionStorage` — they clear when you close the tab
- Prices are pulled from Fuzzwork's Jita 4-4 sell order aggregates
- Assets tab shows all capital components across your inventory
- The Build Cost tab gains two extra columns (In Stock / Need) when logged in
- PI tab shows colony overview — pin counts and last update times
