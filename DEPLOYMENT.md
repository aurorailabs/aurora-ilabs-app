# Firebase Deployment Guide

This guide will help you deploy your Aurora iLabs app to Firebase Hosting.

## Prerequisites

1. A Google account
2. Node.js and npm installed (you already have this)

## Step 1: Install Firebase CLI

Open your terminal and run:

```bash
npm install -g firebase-tools
```

## Step 2: Login to Firebase

```bash
firebase login
```

This will open a browser window for you to authenticate with your Google account.

## Step 3: Initialize Firebase in Your Project

Navigate to your project directory and run:

```bash
firebase init hosting
```

When prompted:
1. **Select "Use an existing project"** (if you have one) or **"Create a new project"** (if you don't)
2. **Select your Firebase project** (or create a new one)
3. **What do you want to use as your public directory?** → Type: `build`
4. **Configure as a single-page app (rewrite all urls to /index.html)?** → Type: `Yes`
5. **Set up automatic builds and deploys with GitHub?** → Type: `No` (unless you want this)
6. **File build/index.html already exists. Overwrite?** → Type: `No`

## Step 4: Build Your React App

```bash
npm run build
```

This creates an optimized production build in the `build` folder.

## Step 5: Deploy to Firebase

```bash
firebase deploy
```

Or use the npm script:

```bash
npm run deploy
```

This will build your app and deploy it to Firebase Hosting.

## Step 6: Access Your Deployed App

After deployment, Firebase will provide you with a URL like:
```
https://your-project-id.web.app
```
or
```
https://your-project-id.firebaseapp.com
```

## Future Deployments

For future updates, simply run:
```bash
npm run deploy
```

This will rebuild and redeploy your app.

## Troubleshooting

### If you get "firebase: command not found"
- Make sure Firebase CLI is installed: `npm install -g firebase-tools`
- Try using `npx firebase` instead of `firebase`

### If routing doesn't work
- Make sure `firebase.json` has the rewrite rule (it's already configured)
- Ensure you're deploying the `build` folder, not `public`

### If build fails
- Make sure all dependencies are installed: `npm install`
- Check for any errors in the build output

## Custom Domain (Optional)

To use a custom domain:
1. Go to Firebase Console → Hosting
2. Click "Add custom domain"
3. Follow the instructions to verify your domain


