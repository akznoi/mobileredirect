# Apple App Site Association for Universal Links

This directory contains the Apple App Site Association (AASA) file needed for iOS Universal Links.

## Quick Deploy to GitHub Pages

1. **Create a new GitHub repository** (e.g., `fordham-universal-links`)

2. **Upload this `.well-known` folder** to the repository

3. **Enable GitHub Pages:**
   - Go to repository Settings → Pages
   - Source: Deploy from a branch
   - Branch: main / root
   - Save

4. **Your AASA file will be available at:**
   ```
   https://yourusername.github.io/fordham-universal-links/.well-known/apple-app-site-association
   ```

5. **Update the AASA file:**
   - Replace `TEAMID` with your Apple Developer Team ID (found in Apple Developer Account)
   - Replace `edu.fordham.myapp` with your actual app bundle identifier

## Alternative: Deploy to Netlify

1. Drag the `.well-known` folder to [Netlify Drop](https://app.netlify.com/drop)
2. Get your URL (e.g., `https://yourapp.netlify.app/.well-known/apple-app-site-association`)

## CAS OIDC Configuration

Once deployed, update your CAS OIDC service registration to include Universal Links:

```json
"redirectUris": [ "java.util.HashSet", [
  "https://yourusername.github.io/fordham-universal-links/callback",
  "myapp://callback"
]]
```

## Testing

Verify your AASA file:
```bash
curl https://yourusername.github.io/fordham-universal-links/.well-known/apple-app-site-association
```

Should return JSON without redirects.
