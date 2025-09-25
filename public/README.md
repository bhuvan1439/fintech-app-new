# Public Assets

This directory contains static assets for the fintech application.

## Contents

This folder is intended to store:

- **Images** - Logos, icons, banners, and other image assets
- **Fonts** - Custom web fonts
- **Icons** - SVG icons and favicon files
- **Documents** - PDF documents, terms of service, privacy policy
- **Manifests** - Web app manifest, sitemap.xml, robots.txt
- **Static Files** - Any other static assets served directly

## Structure

```
public/
├── images/
│   ├── logos/
│   ├── icons/
│   └── banners/
├── fonts/
├── documents/
├── favicon.ico
├── manifest.json
├── robots.txt
└── sitemap.xml
```

## Usage

Files in this directory are served statically and can be accessed directly via URL:

- `public/images/logo.png` → `/images/logo.png`
- `public/favicon.ico` → `/favicon.ico`
- `public/manifest.json` → `/manifest.json`

## Asset Guidelines

### Images
- Use optimized formats (WebP, PNG, SVG)
- Compress images for web
- Use descriptive filenames
- Organize in subdirectories by type

### Icons
- Prefer SVG for scalable icons
- Include multiple favicon sizes
- Use consistent naming conventions

### Fonts
- Include necessary font weights only
- Use web-optimized formats (WOFF2, WOFF)
- Consider font loading performance

## Security Considerations

- Never store sensitive data in public assets
- Ensure all files are meant to be publicly accessible
- Regularly audit for unnecessary or outdated files
- Use appropriate file permissions

## Performance Tips

- Minimize file sizes
- Use CDN for large assets
- Implement proper caching headers
- Consider lazy loading for images

## Accessibility

- Provide alt text for images
- Ensure sufficient color contrast
- Use semantic file names
- Include proper manifest for PWA support
