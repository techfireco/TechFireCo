# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

TechFireCo is a static HTML/CSS website serving as a link-in-bio landing page for affiliate marketing and product recommendations. The site features a responsive grid layout showcasing various tech products, apps, and services with affiliate links.

**Domain**: techfireco.store  
**Hosting**: GitHub Pages  
**Repository**: https://github.com/techfireco/TechFireCo.git

## Development Commands

### Local Development
```bash
# Serve the website locally (requires Python or Node.js)
python3 -m http.server 8000
# OR using Node.js
npx http-server -p 8000

# Open in browser
open http://localhost:8000
```

### Git Operations
```bash
# View recent changes
git --no-pager log --oneline -10

# Check current status
git status

# Add and commit changes
git add .
git commit -m "Description of changes"

# Deploy to GitHub Pages
git push origin main
```

### Image Management
```bash
# Optimize images before adding (recommended for performance)
# Add new product images to the images/ directory
# Ensure images are web-optimized (JPEG/PNG, reasonable file sizes)

# View current images
ls -la images/
```

## Architecture & Structure

### File Organization
- `index.html` - Main landing page with product grid
- `shein-discount.html` - Dedicated guide page for Shein discounts
- `styles.css` - Global stylesheet with responsive design
- `images/` - Product images and assets
- `CNAME` - Custom domain configuration for GitHub Pages

### Core Components

**Main Landing Page (`index.html`)**
- Header with TechFireCo logo
- WhatsApp update section
- Responsive grid layout (3 columns desktop, 2 columns tablet, flexible mobile)
- Product cards with affiliate links
- Affiliate disclaimer footer
- Google Analytics integration (G-BF9ZK52TDB)

**Product Grid System**
- Each product is a `.grid-item` with image and link
- Links use various affiliate platforms: Amazon (amzn.to/openinapp.co), custom short links, direct URLs
- Images are stored locally in the `images/` directory

**Responsive Design**
- Mobile-first approach with CSS media queries
- Breakpoints: 900px (tablet), 1200px (desktop)
- Grid columns adapt: 2 columns ≤900px, 3 columns >900px

### Styling Architecture
- Single CSS file with organized sections
- Custom purple theme (`#c5b2ff` background)
- Consistent card styling with borders and shadows
- Typography: Arial sans-serif stack
- Responsive image handling with `max-width: 100%`

## Content Management

### Adding New Products
1. Add product image to `images/` directory
2. Update `index.html` by adding new `.grid-item` div
3. Follow the existing pattern:
   ```html
   <div class="grid-item">
       <a href="AFFILIATE_LINK">
           <img src="images/PRODUCT_IMAGE.jpeg" alt="Product Description">
       </a>
   </div>
   ```

### Link Management
- Use trackable affiliate links (openinapp.link, amzn.openinapp.co, etc.)
- Maintain consistent alt text for images
- Test all links before deployment

### Blog Content
- Dedicated HTML pages for detailed content (like `shein-discount.html`)
- Self-contained styling within each page
- Follow the established design pattern with step-by-step guides

## Deployment Process

The site automatically deploys to GitHub Pages when changes are pushed to the main branch:

1. Make changes locally
2. Test using local server
3. Commit and push to main branch
4. Changes appear at techfireco.store within minutes

### Domain Configuration
- Custom domain configured via `CNAME` file
- DNS points to GitHub Pages servers
- HTTPS enabled through GitHub Pages

## Development Guidelines

### Image Optimization
- Keep image file sizes reasonable for web performance
- Use descriptive filenames
- Maintain consistent aspect ratios where possible
- Consider WebP format for better compression (with fallbacks)

### Code Style
- Maintain consistent indentation (4 spaces)
- Use semantic HTML structure
- Keep CSS organized by component
- Test responsive behavior across breakpoints

### Affiliate Link Management
- Verify all affiliate links are working
- Use consistent tracking parameters
- Update expired or broken links regularly
- Maintain proper disclosure in footer

### Performance Considerations
- Minimize HTTP requests where possible
- Optimize images before adding
- Keep CSS organized and minimal
- Consider lazy loading for large image sets

## Analytics & Tracking
- Google Analytics configured with ID: G-BF9ZK52TDB
- Track click-through rates on affiliate links
- Monitor site performance and user engagement