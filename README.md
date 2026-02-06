# AI Guides

Dark-mode only site for no-bullshit AI guides. Embedded Claude artifacts, zero fluff.

## Setup

1. **Install Jekyll** (if not already installed):
   ```bash
   gem install bundler jekyll
   ```

2. **Install dependencies**:
   ```bash
   bundle install
   ```

3. **Run locally**:
   ```bash
   bundle exec jekyll serve
   ```
   The site will be available at `http://localhost:4000`

## Deployment to GitHub Pages

1. **Create a GitHub repository** for this project

2. **Push the code**:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
   git push -u origin main
   ```

3. **Enable GitHub Pages**:
   - Go to Settings → Pages in your repository
   - Select "Deploy from a branch"
   - Choose "main" branch and "/ (root)" folder
   - Click Save

4. **Update `_config.yml`**:
   - Set `baseurl: "/YOUR_REPO_NAME"` (if not using custom domain)
   - Set `url: "https://YOUR_USERNAME.github.io"`

5. **Custom Domain** (optional):
   - Create a `CNAME` file with your domain
   - Configure DNS settings with your domain provider

## Adding New Guides

1. Create a new markdown file in `_guides/` directory:
   ```markdown
   ---
   layout: artifact
   title: "Your Guide Title"
   icon: "📚"
   description: "Brief description of your guide"
   date: 2024-01-20
   author: "Your Name"
   permalink: /guides/your-guide-slug/
   ---
   
   <!-- Your artifact embed code here -->
   ```

2. For React-based Claude artifacts:
   - Save the JSX file in `assets/artifacts/`
   - Convert to vanilla JS or use a build process
   - Embed using the React CDN approach shown in the OpenClaw guide

3. For iframe embeds:
   - Add `artifact_url: "URL_TO_ARTIFACT"` to the front matter
   - The layout will automatically create an iframe

## Structure

```
ai-guides-site/
├── _config.yml          # Jekyll configuration
├── _layouts/            # Page layouts
│   ├── default.html     # Base layout
│   └── artifact.html    # Layout for embedded artifacts
├── _guides/             # Guide collection
│   └── openclaw-setup.md
├── assets/
│   ├── css/
│   │   └── style.css    # Site styles
│   └── artifacts/       # Claude artifact files
├── index.html           # Homepage
├── guides.html          # Guides listing page
└── README.md
```

## Notes

- The site is designed to embed Claude artifacts directly
- Each guide can use different embedding methods (iframe, React component, etc.)
- The responsive design works well on mobile and desktop
- Guides are automatically listed on the `/guides` page

## Contributing

To add a new guide:
1. Fork the repository
2. Create your guide in `_guides/`
3. Test locally
4. Submit a pull request

## License

MIT License - feel free to use and modify as needed.# ai-guides
