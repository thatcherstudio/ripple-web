# Ripple Web Page Deployment

This directory contains the web page for the Ripple app, which serves dual purposes:

1. **About Page**: Public-facing information about the Ripple app
2. **OAuth Redirect Handler**: Handles Reddit OAuth callbacks for the iOS app

## Deployment Options

### Option 1: GitHub Pages (Recommended - Free)

1. Create a new repository called `ripple-web` on GitHub
2. Upload the `index.html` file to the repository
3. Enable GitHub Pages in repository settings
4. Your redirect URL will be: `https://yourusername.github.io/ripple-web`

### Option 2: Vercel (Free with custom domain)

```bash
# Install Vercel CLI
npm install -g vercel

# Deploy from this directory
cd web/
vercel --prod
```

### Option 3: Netlify (Free)

1. Drag and drop the `web` folder to Netlify.com
2. Get your deployment URL
3. Optional: Add custom domain

### Option 4: Firebase Hosting (Free tier)

```bash
# Install Firebase CLI
npm install -g firebase-tools

# Initialize Firebase project
firebase init hosting

# Deploy
firebase deploy
```

## Reddit App Configuration

Once deployed, use your web page URL as the OAuth redirect URL in your Reddit app settings:

### Reddit App Settings:
- **App Type**: Installed app
- **Redirect URI**: `https://yourdomain.com` (your deployed page URL)
- **App Name**: Ripple
- **Description**: Personalized Reddit feed with AI summaries

## Testing OAuth Flow

1. Deploy the web page to any hosting service
2. Configure your Reddit app with the deployment URL as redirect URI  
3. Update the iOS app's OAuth configuration with your Reddit client ID
4. Test the authentication flow:
   - iOS app → Reddit OAuth → Web page → Back to iOS app

## Custom Domain (Optional)

For a professional look, consider registering a domain like:
- `rippleapp.com`
- `getripple.app` 
- `ripple.io`

Most hosting providers support custom domains for free.

## Security Notes

- The web page only handles OAuth redirects - no sensitive data is stored
- All authentication tokens are passed directly back to the iOS app
- No server-side processing required - this is a static HTML page