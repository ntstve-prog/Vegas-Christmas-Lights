# Deployment Guide - Vegas Christmas Light Installation Website

This guide covers how to deploy your static HTML website to various hosting platforms.

## Pre-Deployment Checklist

Before deploying, ensure you've completed:

- [ ] Updated all business information (phone, email, hours)
- [ ] Configured LeadConnector form with correct form ID
- [ ] Tested site locally in multiple browsers
- [ ] Verified all links work (phone, email, internal anchors)
- [ ] Tested FAQ accordion functionality
- [ ] Verified mobile responsiveness
- [ ] Checked that logo displays correctly
- [ ] Ensured no console errors in browser

## Domain Setup

### Recommended Domain
- `vegaschristmaslightinstall.com` or similar Las Vegas-focused domain
- Alternative: `lasvegaschristmaslights.com`

**Important:** Use a completely different domain than the Surprise site to maintain SEO isolation.

### Domain Registrars
- **Namecheap** (recommended for value)
- **GoDaddy** (most popular)
- **Google Domains** (if still available)
- **Cloudflare** (includes free DNS and CDN)

## Hosting Options

### Option 1: Netlify (Recommended for Ease)

**Why Netlify:**
- Free tier available
- Automatic HTTPS
- Excellent performance
- Simple deployment
- Form handling built-in

**Deployment Steps:**

1. **Sign up** at netlify.com

2. **Deploy via Drag & Drop:**
   - Go to Netlify dashboard
   - Drag the entire `vegas-christmas-lights-site` folder onto the dashboard
   - Netlify will upload and deploy automatically
   - You'll get a random URL like `random-name-123.netlify.app`

3. **Connect Custom Domain:**
   - Go to Site settings > Domain management
   - Click "Add custom domain"
   - Enter your domain (e.g., `vegaschristmaslightinstall.com`)
   - Follow DNS configuration instructions
   - Netlify provides automatic HTTPS

4. **Configure Redirects (optional):**
   Create a `_redirects` file in your site folder:
   ```
   # Redirect www to non-www
   https://www.vegaschristmaslightinstall.com/*  https://vegaschristmaslightinstall.com/:splat  301!
   ```

**Cost:** Free for basic usage

---

### Option 2: Vercel

**Why Vercel:**
- Free tier
- Extremely fast CDN
- Simple deployment
- Automatic HTTPS

**Deployment Steps:**

1. Sign up at vercel.com
2. Click "New Project"
3. Drag & drop your site folder
4. Add custom domain in project settings
5. Configure DNS as instructed

**Cost:** Free for personal/small business use

---

### Option 3: GitHub Pages

**Why GitHub Pages:**
- Completely free
- Works well with static sites
- Good for version control

**Deployment Steps:**

1. Create a GitHub account
2. Create a new repository named `vegas-christmas-lights`
3. Upload your site files to the repository
4. Go to Settings > Pages
5. Select main branch as source
6. Add custom domain in settings
7. Configure DNS:
   - Add CNAME record pointing to `username.github.io`

**Cost:** Free

---

### Option 4: Cloudflare Pages

**Why Cloudflare Pages:**
- Free tier
- Fastest CDN globally
- Built-in analytics
- Excellent security

**Deployment Steps:**

1. Sign up at cloudflare.com
2. Go to Pages
3. Create new project
4. Upload files directly or connect to Git
5. Configure custom domain
6. Cloudflare automatically handles DNS if you use their nameservers

**Cost:** Free

---

### Option 5: Traditional Web Hosting (cPanel)

**Providers:**
- Bluehost
- SiteGround
- HostGator
- DreamHost

**Deployment Steps:**

1. Purchase hosting plan
2. Access cPanel
3. Go to File Manager
4. Navigate to `public_html` folder
5. Upload all files from `vegas-christmas-lights-site` folder:
   - `index.html`
   - `assets/` folder with logo and favicon
6. Visit your domain - site should be live

**Cost:** $3-10/month typically

---

## DNS Configuration

Regardless of hosting choice, you'll need to configure DNS. Here's what you'll typically need:

### For Netlify/Vercel/Cloudflare Pages
```
Type: A
Name: @
Value: [Provided by host]

Type: CNAME
Name: www
Value: [your-site].netlify.app (or similar)
```

### For Traditional Hosting
```
Type: A
Name: @
Value: [Your server IP]

Type: CNAME
Name: www
Value: @
```

**DNS Propagation:** Can take 1-48 hours (usually under 6 hours)

## SSL/HTTPS Setup

**Modern Hosting (Netlify, Vercel, Cloudflare):**
- Automatic HTTPS - no configuration needed

**Traditional Hosting:**
- Most hosts offer free Let's Encrypt SSL
- Enable in cPanel > SSL/TLS
- Or contact support to enable

**Important:** Always use HTTPS for better SEO and security.

## Performance Optimization (Post-Deployment)

### 1. Enable Compression
Most modern hosts enable this automatically. For traditional hosting:
- Verify gzip compression is enabled
- Check in cPanel > Optimize Website

### 2. Set Cache Headers
For traditional hosting, add to `.htaccess`:
```apache
<IfModule mod_expires.c>
  ExpiresActive On
  ExpiresByType image/png "access plus 1 year"
  ExpiresByType text/html "access plus 0 seconds"
  ExpiresByType text/css "access plus 1 year"
  ExpiresByType application/javascript "access plus 1 year"
</IfModule>
```

### 3. Use a CDN
- Cloudflare (free tier): Best option
  - Sign up at cloudflare.com
  - Add your site
  - Change nameservers at your registrar
  - Automatic CDN + security

## Google Analytics Setup

1. Create Google Analytics 4 property at analytics.google.com
2. Get your Measurement ID (format: `G-XXXXXXXXXX`)
3. Add before `</head>` in index.html:

```html
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

## Google Search Console Setup

After deployment:

1. Go to search.google.com/search-console
2. Add property for your domain
3. Verify ownership (usually via DNS TXT record)
4. Submit sitemap (see below)

### Creating a Sitemap

Create `sitemap.xml` in your root directory:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://vegaschristmaslightinstall.com/</loc>
    <lastmod>2024-11-01</lastmod>
    <changefreq>monthly</changefreq>
    <priority>1.0</priority>
  </url>
</urlset>
```

Submit this sitemap URL in Google Search Console.

## robots.txt

Create `robots.txt` in root directory:

```
User-agent: *
Allow: /

Sitemap: https://vegaschristmaslightinstall.com/sitemap.xml
```

## Testing After Deployment

### 1. Functional Testing
- [ ] Visit site on desktop
- [ ] Visit site on mobile
- [ ] Click all phone numbers - they should dial
- [ ] Click email - should open email client
- [ ] Test form submission
- [ ] Test FAQ accordion
- [ ] Test all anchor links (#quote, etc.)

### 2. Performance Testing
- Visit PageSpeed Insights: developers.google.com/speed/pagespeed/insights
- Enter your URL
- Aim for 90+ on mobile, 95+ on desktop

### 3. SEO Testing
- Google "site:yourdomain.com" - should show your page
- Check meta title shows in search results
- Verify meta description appears

### 4. Mobile Responsiveness
- Visit on actual phone
- OR use Chrome DevTools (F12 > Toggle device toolbar)
- Test on multiple screen sizes

## Ongoing Maintenance

### Monthly Tasks
- [ ] Check Google Analytics for traffic
- [ ] Monitor form submissions in LeadConnector
- [ ] Check Search Console for errors
- [ ] Verify site still loads correctly

### Seasonal Updates
- Before holiday season starts:
  - [ ] Update any pricing
  - [ ] Refresh any seasonal messaging
  - [ ] Ensure form is routing correctly

### Annual Tasks
- [ ] Renew domain registration
- [ ] Renew hosting (if using paid hosting)
- [ ] Update copyright year in footer (automatic via JavaScript)

## Troubleshooting

### Site Not Loading
1. Check DNS configuration
2. Wait for DNS propagation (up to 48 hours)
3. Clear browser cache
4. Try incognito/private browsing mode

### Form Not Working
1. Verify correct form ID in iframe
2. Check browser console for errors
3. Test LeadConnector form directly
4. Ensure form script is loading

### Poor Mobile Performance
1. Test on real device, not just DevTools
2. Check PageSpeed Insights recommendations
3. Ensure images are optimized (logo should be <1MB)

### SSL Certificate Issues
1. Contact hosting provider
2. Verify domain is correctly pointed
3. Force HTTPS redirect if needed

## Support Resources

- **Netlify Docs:** docs.netlify.com
- **Vercel Docs:** vercel.com/docs
- **Cloudflare Docs:** developers.cloudflare.com
- **GitHub Pages Docs:** docs.github.com/pages

## Cost Summary

**Minimum Annual Cost (Using Free Hosting):**
- Domain: $10-15/year
- Hosting: $0 (Netlify/Vercel/GitHub Pages)
- **Total: ~$12-15/year**

**Professional Setup:**
- Domain: $10-15/year
- Hosting: $60-120/year (traditional web host)
- Cloudflare Pro (optional): $20/month
- **Total: ~$70-300/year**

**Recommendation:** Start with free hosting (Netlify) + domain. Upgrade later if needed.

## Final Notes

1. **Always keep a backup** of your site files locally
2. **Test thoroughly** before deploying
3. **Monitor analytics** to track performance
4. **Keep SEO isolation** - never link to/from the Surprise site
5. **Update content seasonally** to maintain relevance

For additional help, refer to your hosting provider's documentation or support team.
