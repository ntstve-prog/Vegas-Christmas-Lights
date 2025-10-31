# Vegas Christmas Light Installation Website

A high-performance, SEO-optimized single-page website for Vegas Christmas Light Installation services in Las Vegas, Nevada.

## Overview

This is a standalone static HTML site designed for maximum performance and conversion optimization. Built with direct response marketing principles and completely isolated from the Surprise, AZ site to avoid any SEO conflicts.

## Business Information

- **Business Name:** Vegas Christmas Light Installation
- **Phone:** (702) 527-2242
- **Email:** vegaschristmaslightinstall@gmail.com
- **Service Area:** Las Vegas, Henderson, Summerlin, North Las Vegas, and surrounding Las Vegas Valley communities

## Project Structure

```
vegas-christmas-lights-site/
├── index.html          # Main website file (production-ready)
├── assets/
│   ├── logo.png       # Vegas Christmas Light Installation logo
│   └── favicon.svg    # Site favicon
├── README.md          # This file
└── DEPLOYMENT.md      # Hosting and deployment instructions
```

## Features

### Technical Features
- **Single-page HTML** - No build process required, just upload and go
- **Inline Critical CSS** - Above-the-fold styles inline for fast First Contentful Paint
- **Mobile-first responsive design** - Optimized for all screen sizes
- **Optimized animations** - CSS-only animations for smooth performance
- **Accessible** - ARIA labels, keyboard navigation support, semantic HTML
- **Fast loading** - Minimal JavaScript, optimized for PageSpeed scores

### SEO Isolation (Zero Conflicts with Surprise Site)
- ✅ Unique title tags and meta descriptions (Las Vegas focused)
- ✅ Unique H1 and all heading content
- ✅ Las Vegas-specific schema markup with NV address
- ✅ Unique meta keywords
- ✅ All unique alt text on images
- ✅ Las Vegas geographic targeting in metadata
- ✅ Different business name and contact info
- ✅ Completely rewritten copy (maintains tone, unique content)
- ✅ Different service areas (Vegas Valley vs West Valley)
- ✅ Unique FAQ content

### Page Sections

1. **Header** - Sticky navigation with logo, hours, phone, and CTA
2. **Hero** - Animated snowflakes and Christmas lights with lead capture form
3. **Service Packages** - Three tiers (Rooflines, Full Property, Commercial)
4. **How We Work** - 3-step process with trust-building messaging
5. **Service Areas** - 12 Las Vegas Valley neighborhoods
6. **FAQ** - 7 common questions with accordion interaction
7. **Final CTA** - Last conversion opportunity before footer
8. **Footer** - Contact info and branding

## How to Update Content

### Updating Business Hours
Find this line in the `<header>` section (around line 765):
```html
<div class="hours-text">Open 8am-6pm every day</div>
```

### Updating Phone Number
Search and replace all instances of:
- `7025272242` (in tel: links)
- `(702) 527-2242` (displayed number)

### Updating Email
Search and replace: `vegaschristmaslightinstall@gmail.com`

### Adding/Removing Service Areas
Find the Service Areas section (around line 2753). Each area follows this pattern:
```html
<div class="area-card">
  <div class="area-icon">
    <!-- SVG icon -->
  </div>
  <h3 class="area-name">Area Name</h3>
</div>
```

### Updating Package Pricing or Features
Find the Service Packages section (around line 2427). Each package has a list of features:
```html
<li class="feature-item">
  <svg class="check-icon"><!-- checkmark --></svg>
  <span>Feature description here</span>
</li>
```

### Updating FAQ Questions
Find the FAQ section (around line 2903). Each FAQ follows this structure:
```html
<div class="faq-item">
  <button class="faq-question-button" aria-expanded="false" aria-controls="faq-X">
    <span class="faq-question-text">Question here?</span>
    <!-- Icon -->
  </button>
  <div class="faq-answer" id="faq-X" aria-hidden="true">
    <div class="faq-answer-content">
      <p>Answer here.</p>
    </div>
  </div>
</div>
```

**Important:** When adding FAQ items, increment the `faq-X` ID numbers and ensure `aria-controls` matches the answer `id`.

## Color Scheme

The site uses a Christmas-themed color palette:

- **Red:** `#DC2626` (primary CTA color)
- **Green:** `#16A34A` (secondary/trust color)
- **Yellow:** `#FBBF24` (accent, lights)
- **Dark:** `#111827` (text, dark sections)
- **White:** `#FFFFFF` (backgrounds, text on dark)

These match the original Surprise site for brand consistency while maintaining separate content.

## Form Integration

The site uses LeadConnector (GHL) for lead capture:
- **Form ID:** `RyiXDbmrL1ULrGjXAc1B`
- **Form Location:** Hero section (top of page)
- **Script:** `https://link.msgsndr.com/js/form_embed.js`

To update the form, replace the form ID in the `<iframe>` tag around line 930.

## Browser Compatibility

Tested and working in:
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+
- Mobile browsers (iOS Safari, Chrome Mobile)

## Performance Optimization

Current optimizations:
- Critical CSS inlined
- Minimal JavaScript (FAQ accordion only)
- CSS-only animations for snowflakes and lights
- System font stack (no web font loading)
- SVG icons (no icon font files)
- Smooth scroll behavior via CSS

**Target Performance:**
- First Contentful Paint: < 1.5s
- Largest Contentful Paint: < 2.5s
- PageSpeed Score: 95+ mobile, 100 desktop

## Local Development

No build process needed! Simply:

1. Open `index.html` in your browser
2. Make changes to the HTML
3. Refresh browser to see updates

## Testing Checklist

- [ ] All phone numbers dial correctly on mobile
- [ ] Email link opens mail client
- [ ] Form submissions work and route to correct GHL account
- [ ] FAQ accordion opens/closes smoothly
- [ ] All internal links (e.g., #quote) scroll correctly
- [ ] Site is mobile responsive (test on phone)
- [ ] Logo displays correctly
- [ ] All animations perform smoothly
- [ ] No console errors

## SEO Checklist

- [x] Unique page title (different from Surprise site)
- [x] Unique meta description
- [x] Unique H1 tag
- [x] Las Vegas-specific keywords
- [x] LocalBusiness schema with Vegas address
- [x] Unique alt text on logo
- [x] Geographic coordinates in schema
- [x] Service area markup (Vegas Valley)
- [x] Canonical URL configured
- [x] No duplicate content with Surprise site

## Support

For questions or issues:
- Review this README
- Check DEPLOYMENT.md for hosting questions
- Refer to the original Surprise site for design reference

## License

Proprietary - Vegas Christmas Light Installation
© 2024 All rights reserved
