# PinkPong — GitHub Pages Deployment

This repository contains a single-file browser game (index.html). I added an automated GitHub Actions workflow to publish the site to GitHub Pages.

Preview URL (once deployed):
https://StormMultimedia.github.io/pinkpong/

What I added
- .github/workflows/pages.yml — GitHub Actions workflow that uploads the repository root as a Pages site using the official actions/upload-pages-artifact and actions/deploy-pages actions.
- README.md (this file) with instructions and the preview URL.

How it works
1. When you push to the main branch the workflow will run and upload the repository contents as a Pages artifact, then deploy it.
2. After the first successful run the site should be available at the preview URL above (usually within a minute or two).

Notes and troubleshooting
- Public vs Private repo: If the repository is public the Pages site should work automatically. If the repository is private, you may need to enable GitHub Pages or adjust repository visibility/permissions in Settings → Pages.
- First-time audio playback on mobile: mobile browsers often require a user interaction (tap) before the WebAudio API will play sound.
- If you prefer Pages to serve from the `main` branch root instead of the gh-pages artifact the workflow can be adjusted, or you can enable branch-based Pages from the repo Settings → Pages.
- To force a redeploy, make any small change and push to `main` (this triggers the workflow).

Security
- The workflow uses the built-in `GITHUB_TOKEN` and the official `actions/deploy-pages` action. No secrets are required.

If you'd like I can also:
- Update the workflow to only publish the `dist/` folder (if you add a build step). 
- Configure a custom domain (CNAME) file and instructions.
