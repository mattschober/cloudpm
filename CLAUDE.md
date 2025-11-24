# CLAUDE.md - AI Assistant Guide

## Repository Overview

This repository contains the professional consulting website for **Matt Schober - Cloud Project Management Expert**. The site showcases enterprise cloud consulting services, specializing in AWS/Azure migrations and disaster recovery planning.

**Primary Domain:** mattschober-cloudpm.com
**Alternate Domain:** migratewithmatt.com
**Deployment:** GitHub Pages
**Tech Stack:** Static HTML/CSS/JavaScript (no build process)

---

## Repository Structure

```
cloudpm/
├── index.html                          # Main landing page (all-in-one HTML/CSS/JS)
├── scheduled.html                      # Meeting confirmation page
├── images/                             # Asset directory
│   ├── consulting-logo-dark-compressed.jpg  # Favicon
│   ├── hero-video.mp4                  # Hero section background video
│   ├── social-share.png                # Social media preview (1200x630px)
│   ├── aws-*.png                       # AWS certification badges
│   ├── azure-partner-logo-schober.png  # Azure partner badge
│   └── pmi-*.png                       # PMI certification badges
├── schober-consulting-logo-dark.png    # Company logo (displays on page)
├── .htaccess                           # Apache server configuration
├── robots.txt                          # Search engine & AI crawler rules
├── sitemap.xml                         # SEO sitemap
├── CNAME                               # GitHub Pages domain config
├── README.md                           # Project overview
├── DEPLOYMENT_GUIDE.txt                # Deployment instructions
├── FILE_CHECKLIST.txt                  # Deployment file requirements
└── LOGO_INSTRUCTIONS.txt               # Logo placement guide
```

---

## Project Architecture

### Technology Approach
- **Single-File Architecture**: index.html contains all HTML, CSS, and JavaScript in one file for simplicity
- **No Build Process**: Direct deployment without compilation or bundling
- **Static Hosting**: Designed for GitHub Pages, but compatible with any static host
- **Mobile-First Responsive**: CSS media queries for all screen sizes

### Key Features
- Video background hero section
- Smooth scroll navigation to anchor sections
- Embedded HubSpot forms for lead capture
- Google Analytics integration (G-YF9VXB9YLV)
- Schema.org structured data for AI/SEO
- Open Graph and Twitter Card meta tags
- Comprehensive security headers in .htaccess

### Page Sections (index.html)
1. **Hero** - Video background with name, logo, tagline
2. **About** - Professional background and value proposition
3. **Services** - Six core service offerings
4. **Experience** - Career highlights (Slalom, Deloitte)
5. **Certifications** - AWS, Azure, PMI badges
6. **Contact** - Email, LinkedIn, scheduling links

---

## Development Conventions

### HTML/CSS Standards
- **Semantic HTML5**: Use proper semantic elements (`<section>`, `<article>`, `<nav>`)
- **BEM-like Naming**: Classes follow `.section-element` pattern (e.g., `.hero-title`, `.service-card`)
- **Mobile-First**: Base styles for mobile, media queries for larger screens
- **Accessibility**: Include ARIA labels, alt text, and semantic structure

### Image Requirements
- **social-share.png**: 1200 × 630 pixels (Open Graph standard)
- **consulting-logo-dark-compressed.jpg**: Optimized favicon (32×32 or 64×64px)
- **schober-consulting-logo-dark.png**: Main logo (~200×200px, responsive)
- **hero-video.mp4**: Optimized for web, MP4 format, autoplay compatible

### SEO & Metadata
- All meta tags in `<head>` section of index.html
- Schema.org JSON-LD structured data (3 types: ProfessionalService, ItemList, Person)
- Geographic targeting: Saint Paul, MN (geo tags included)
- AI crawler optimization: robots.txt explicitly allows GPTBot, Claude-Web, etc.

### Security Headers (.htaccess)
```apache
X-Content-Type-Options: nosniff
X-Frame-Options: SAMEORIGIN
X-XSS-Protection: 1; mode=block
Referrer-Policy: strict-origin-when-cross-origin
```

---

## Git Workflow

### Branching Strategy
- **Main Branch**: Production-ready code
- **Feature Branches**: Named `claude/claude-md-*` for AI assistant work
- **Direct Commits**: Small changes can go directly to main (single maintainer)

### Commit Message Pattern
Based on recent history, commits use simple descriptive messages:
- "Add files via upload" (bulk changes)
- "Add Cert Section" (feature additions)
- "Update index.html" (content updates)

**Recommendation**: Use more descriptive commits like:
- "feat: Add Azure certification badges to homepage"
- "fix: Update contact email in footer"
- "docs: Update deployment guide with SSL instructions"

### Deployment Process
1. Commit changes to git
2. Push to GitHub repository
3. GitHub Pages automatically deploys from main branch
4. Verify at https://mattschober-cloudpm.com

---

## Common Modification Tasks

### Updating Contact Information
**File:** `index.html`
**Locations to update:**
- Meta tags (lines ~10-12)
- Schema.org structured data (lines ~70, 95, 272)
- Contact section (search for "DR@migratewithmatt.com")
- Footer

### Adding New Services
**File:** `index.html`
**Process:**
1. Add service card in Services section (follow existing `.service-card` structure)
2. Update Schema.org ItemList (add new ListItem)
3. Update meta description if it's a major service
4. Test responsive layout on mobile

### Updating Certifications
**File:** `index.html`
**Process:**
1. Add certification image to `/images/` directory
2. Add `<img>` tag in Certifications section
3. Update Schema.org hasCredential array
4. Optimize image size (use compressed PNG/JPG)

### Changing Domain
**Files:** `.htaccess`, `CNAME`, `robots.txt`, `sitemap.xml`, `index.html`
**Process:**
1. Update CNAME file with new domain
2. Update all absolute URLs in meta tags
3. Update sitemap.xml locations
4. Update robots.txt sitemap URL
5. Configure DNS CNAME record to point to GitHub Pages

---

## AI Assistant Guidelines

### When Making Changes

1. **ALWAYS Read First**: Use Read tool on index.html before suggesting changes
2. **Preserve Structure**: This is a single-file architecture - don't split into multiple files without explicit request
3. **Test Responsiveness**: Consider mobile, tablet, and desktop layouts
4. **Maintain SEO**: Update meta tags and structured data when changing content
5. **Check All Instances**: Contact info appears in multiple places - update everywhere

### Content Guidelines

1. **Professional Tone**: B2B enterprise consulting language (Fortune 500 clients)
2. **Target Audience**: Mid-market to enterprise CTOs, IT Directors, Operations Managers
3. **Geographic Focus**: United States, particularly Minnesota/Midwest
4. **Service Focus**: Disaster recovery, cloud migration (AWS/Azure), project management
5. **Avoid Marketing Fluff**: Be specific, technical, and credible

### Code Modifications

1. **Inline Styles**: All CSS is in `<style>` tags in `<head>` - keep it there
2. **JavaScript**: Minimal JS in `<script>` tags at end of `<body>` - keep simple
3. **Dependencies**: No external dependencies except Google Analytics and HubSpot embeds
4. **Performance**: Keep total page size under 100KB (excluding video)
5. **Compatibility**: Target modern browsers, but gracefully degrade

### Image Handling

1. **Compression**: Always compress images before suggesting upload
2. **Format**: Use JPEG for photos, PNG for logos/graphics with transparency
3. **Naming**: Use descriptive kebab-case names (e.g., `aws-solutions-architect.png`)
4. **Alt Text**: Always include descriptive alt text for accessibility
5. **Lazy Loading**: Consider adding loading="lazy" for below-fold images

---

## Testing Checklist

Before committing changes, verify:

- [ ] **Responsive Design**: Test at 320px, 768px, 1024px, 1920px widths
- [ ] **Links Work**: All internal anchors and external links functional
- [ ] **Images Load**: All images display with correct aspect ratios
- [ ] **SEO Validation**: Test with https://search.google.com/test/rich-results
- [ ] **Mobile-Friendly**: Test with https://search.google.com/test/mobile-friendly
- [ ] **Accessibility**: Check color contrast, ARIA labels, semantic HTML
- [ ] **Performance**: Page loads in under 3 seconds on 3G connection
- [ ] **Cross-Browser**: Test in Chrome, Firefox, Safari, Edge

---

## Key URLs & Resources

### Live Sites
- **Primary:** https://mattschober-cloudpm.com
- **Alternate:** https://migratewithmatt.com

### Social Profiles
- **LinkedIn:** https://linkedin.com/in/mattschober
- **Twitter/X:** https://x.com/migratewithmatt
- **Crunchbase:** https://www.crunchbase.com/person/matt-schober-7c48

### Tools & Services
- **Analytics:** Google Analytics (G-YF9VXB9YLV)
- **Forms:** HubSpot embedded forms
- **Hosting:** GitHub Pages
- **Email:** DR@migratewithmatt.com

### Testing Tools
- **Rich Results:** https://search.google.com/test/rich-results
- **Mobile-Friendly:** https://search.google.com/test/mobile-friendly
- **Page Speed:** https://pagespeed.web.dev/
- **SEO Checker:** https://www.seobility.net/en/seocheck/

---

## Deployment Instructions

### GitHub Pages Deployment
1. Push changes to main branch
2. GitHub Pages auto-deploys in 1-2 minutes
3. Verify at https://mattschober-cloudpm.com
4. Clear CDN cache if changes don't appear (wait 5-10 minutes)

### Manual Deployment (Alternative Hosts)
See `DEPLOYMENT_GUIDE.txt` for detailed instructions on:
- FTP/SFTP deployment
- cPanel File Manager upload
- SSH/command-line deployment
- Post-deployment verification

### DNS Configuration
- **A Records:** Point to GitHub Pages IP addresses
- **CNAME Record:** `mattschober-cloudpm.com` → `[username].github.io`
- **SSL:** GitHub Pages provides automatic SSL
- **Redirect:** .htaccess forces HTTPS and removes www

---

## Troubleshooting

### Common Issues

**Images Not Loading**
- Check file paths are relative (e.g., `images/logo.png`)
- Verify files are committed to git
- Clear browser cache (Ctrl+F5 or Cmd+Shift+R)
- Check case sensitivity (Linux servers are case-sensitive)

**Styles Not Applying**
- Verify CSS is within `<style>` tags in `<head>`
- Check for syntax errors (missing semicolons, brackets)
- Clear browser cache
- Check browser console for errors

**.htaccess Not Working**
- Only works on Apache servers (not Nginx)
- Check file is named exactly `.htaccess` (with leading dot)
- Verify file permissions (should be 644)
- Nginx users need nginx.conf instead

**Schema.org Validation Errors**
- Test at https://search.google.com/test/rich-results
- Check JSON-LD syntax (commas, brackets, quotes)
- Validate required properties for each schema type
- Ensure no trailing commas in JSON

**GitHub Pages Not Updating**
- Wait 5-10 minutes for deployment
- Check GitHub Actions tab for build status
- Verify CNAME file contains correct domain
- Clear browser cache and CDN cache

---

## Business Context

### Target Market
- **Company Size:** Mid-market to enterprise (100+ employees)
- **Industries:** Healthcare, financial services, manufacturing, technology, retail
- **Budget Range:** $$$$ (enterprise pricing)
- **Geographic:** United States (focus on Midwest)

### Competitive Positioning
- **Not a Dev Shop:** Project management, not hands-on coding
- **Enterprise Focus:** Fortune 500 experience, not SMB/startup
- **Specialized Services:** Disaster recovery and cloud migration, not general IT
- **Partner-Backed:** AWS & Azure partner status, PMI certified

### Conversion Goals
1. **Email Contact:** DR@migratewithmatt.com
2. **LinkedIn Connection:** Direct messaging via LinkedIn
3. **Meeting Scheduling:** HubSpot form submissions
4. **AI Discovery:** Schema.org data for AI assistants to recommend services

---

## Version History

### Current Version (2025-11-24)
- Added recent certifications section
- Updated structured data
- Enhanced AI crawler optimization
- Improved mobile responsiveness

### Future Enhancements (Suggested)
- [ ] Add case studies/portfolio section
- [ ] Implement testimonials slider
- [ ] Add blog/articles section for SEO
- [ ] Create downloadable disaster recovery checklist
- [ ] Add chatbot for initial qualification
- [ ] Implement dark mode toggle
- [ ] Add video testimonials

---

## Contact & Support

**Repository Owner:** Matt Schober
**Business Email:** DR@migratewithmatt.com
**Website Issues:** Create issue in GitHub repository
**General Inquiries:** Contact via email or LinkedIn

---

## Additional Notes for AI Assistants

### Philosophy
This website prioritizes:
1. **Clarity over Cleverness**: Direct, professional language
2. **Performance over Features**: Fast loading, minimal dependencies
3. **Accessibility over Aesthetics**: Readable, semantic, accessible
4. **Conversion over Traffic**: Quality leads over quantity

### When in Doubt
1. **Read the existing code** - patterns are consistent throughout
2. **Check README.md** - business context and technical details
3. **Review DEPLOYMENT_GUIDE.txt** - deployment and hosting specifics
4. **Validate changes** - use testing tools before committing
5. **Ask questions** - clarify requirements before making assumptions

### Red Flags (Don't Do This)
- ❌ Don't add external dependencies (jQuery, Bootstrap, etc.)
- ❌ Don't split into multiple HTML files without explicit request
- ❌ Don't change the brand voice to be casual or startup-y
- ❌ Don't remove schema.org structured data
- ❌ Don't suggest removing AI crawler permissions
- ❌ Don't add complex JavaScript frameworks
- ❌ Don't compromise mobile responsiveness for desktop features

### Green Lights (Do This)
- ✅ Compress and optimize images
- ✅ Improve accessibility (ARIA, semantic HTML, color contrast)
- ✅ Enhance SEO metadata and structured data
- ✅ Suggest performance optimizations
- ✅ Improve responsive design across breakpoints
- ✅ Add relevant certifications and credentials
- ✅ Update outdated information
- ✅ Fix broken links or validation errors

---

**Last Updated:** 2025-11-24
**Maintained By:** Matt Schober / AI Assistants
**Version:** 1.0
