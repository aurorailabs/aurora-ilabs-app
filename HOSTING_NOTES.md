# Hosting Configuration Notes

## Current Hosting: Hostinger

This project is configured for **Hostinger** hosting.

## Important Files for Hostinger

### Required Files:
- **`.htaccess`** - Located in `public/.htaccess` (automatically copied to build folder)
  - Handles React Router client-side routing
  - Enables GZIP compression
  - Configures browser caching
  - Sets security headers

- **`sitemap.xml`** - Located in `public/sitemap.xml` (automatically copied to build folder)
  - Helps search engines index your site

- **`robots.txt`** - Located in `public/robots.txt` (automatically included in build)
  - Guides search engine crawlers

## Build Process

When you run `npm run build:hostinger`, it will:
1. Build the React app for production
2. Copy `.htaccess` to the build folder
3. Copy `sitemap.xml` to the build folder
4. All other files are automatically included

## Firebase Configuration

The `firebase.json` file is present but **not used** for Hostinger hosting. You can:
- Keep it if you might switch to Firebase in the future
- Delete it if you're certain you'll only use Hostinger

## Deployment Steps

1. Run: `npm run build:hostinger`
2. Upload everything from the `build/` folder to Hostinger's `public_html/` directory
3. Ensure `.htaccess` is uploaded (it might be hidden - enable "Show hidden files" in File Manager)

See `DEPLOYMENT.md` for detailed instructions.

