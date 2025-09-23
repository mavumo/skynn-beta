# GitHub Pages Deployment

This repository is configured to automatically deploy to GitHub Pages with a custom domain.

## Setup

### Custom Domain
The app is configured to deploy to `app.skinlabs.co.za`. The domain is set in the `public/CNAME` file.

### Build Process
- The GitHub Actions workflow in `.github/workflows/deploy.yml` automatically builds and deploys the app on pushes to the `main` or `master` branch
- Uses Node.js 18 and npm for dependency management
- Builds only the client-side app using `npm run build:client`
- Deploys the `dist/public` directory to GitHub Pages

### Manual Deployment
To manually build and deploy:

1. Install dependencies: `npm install`
2. Build the client: `npm run build:client`
3. The output will be in `dist/public/` ready for static hosting

### GitHub Pages Configuration
In your repository settings:
1. Go to Settings > Pages
2. Set Source to "GitHub Actions"
3. The workflow will handle the deployment

### Custom Domain Setup
1. In your DNS provider, create a CNAME record pointing `app.skinlabs.co.za` to `jobbyist.github.io`
2. In GitHub repository settings > Pages > Custom domain, enter `app.skinlabs.co.za`
3. Enable "Enforce HTTPS"

The CNAME file in the public directory ensures the custom domain is maintained after each deployment.