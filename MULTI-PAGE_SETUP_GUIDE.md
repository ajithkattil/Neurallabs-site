# Multi-Page Website Setup Guide for neurallabs.us

## 📁 File Structure

Here's how your GitHub repository should be organized:

```
your-github-repo/
├── index.html              ← Homepage
├── about.html              ← About page
├── services.html           ← Services page
├── portfolio.html          ← Portfolio/Projects
├── blog.html               ← Blog listing
├── contact.html            ← Contact page
├── style.css               ← Shared stylesheet
├── neural_labs_logo.svg    ← Your logo
└── README.md               ← Optional
```

## 🚀 Quick Setup (5 Steps)

### Step 1: Upload All Files to GitHub

1. Go to your GitHub repository
2. Click "Add file" → "Upload files"
3. Drag and drop ALL these files:
   - `index.html`
   - `about.html`
   - `services.html`
   - `portfolio.html`
   - `blog.html`
   - `contact.html`
   - `style.css`
   - `neural_labs_logo.svg`
4. Click "Commit changes"

### Step 2: Wait for GitHub Pages to Deploy

- GitHub will automatically rebuild your site (takes 1-2 minutes)
- You'll see a yellow dot turn to green checkmark when done
- Check: Settings → Pages to see deployment status

### Step 3: Test Your Pages

Your pages will now be live at:
- `https://neurallabs.us/` (Homepage)
- `https://neurallabs.us/about.html`
- `https://neurallabs.us/services.html`
- `https://neurallabs.us/portfolio.html`
- `https://neurallabs.us/blog.html`
- `https://neurallabs.us/contact.html`

### Step 4: Set Up Forms (Formspree)

1. Go to [formspree.io](https://formspree.io)
2. Sign up for free account
3. Create two forms:
   - **Contact Form** (for contact.html and index.html)
   - **Newsletter Form** (for blog.html and index.html)
4. Get your form IDs (looks like: `xyzabc123`)
5. Replace in ALL files:
   - Find: `YOUR_FORM_ID`
   - Replace with: your actual contact form ID
   - Find: `YOUR_NEWSLETTER_FORM_ID`
   - Replace with: your actual newsletter form ID

### Step 5: Update Social Media Links

In ALL HTML files, find and update:
```html
https://twitter.com/neurallabs        → your actual Twitter/X
https://linkedin.com/company/neurallabs → your actual LinkedIn
https://github.com/neurallabs          → your actual GitHub
```

## 🎨 How It Works

### Shared Navigation

All pages use the same navigation menu. The current page is highlighted with the `active` class:

```html
<nav>
  <a href="index.html">Home</a>
  <a href="about.html">About</a>
  <a href="services.html" class="active">Services</a>  ← highlighted
  <a href="portfolio.html">Portfolio</a>
  <a href="blog.html">Blog</a>
  <a href="contact.html">Contact</a>
</nav>
```

### Shared Styles (style.css)

All pages link to the same CSS file:
```html
<link rel="stylesheet" href="style.css">
```

This means:
- ✅ Consistent design across all pages
- ✅ Easy to update colors/fonts in one place
- ✅ Faster loading (browser caches the CSS)

### Logo Links Back to Home

On all pages, clicking the logo returns to homepage:
```html
<a href="index.html">
  <img src="neural_labs_logo.svg" alt="Neural Labs" class="logo">
</a>
```

## 📝 Customization Guide

### Changing Colors

Edit `style.css` and update these variables:
```css
:root{
  --accent1:#7c3aed;  /* Purple - change to your brand color */
  --accent2:#06b6d4;  /* Cyan - change to your secondary color */
  --muted:#94a3b8;    /* Gray text color */
}
```

### Adding More Pages

1. Copy any existing HTML file
2. Rename it (e.g., `pricing.html`)
3. Update the `<title>` and content
4. Add link to navigation in ALL files:
```html
<nav>
  <a href="index.html">Home</a>
  <a href="about.html">About</a>
  <a href="services.html">Services</a>
  <a href="pricing.html">Pricing</a>  ← new page
  ...
</nav>
```

### Creating Blog Posts

1. Create a folder called `blog` in your repo
2. Create individual post files: `blog/post-1.html`
3. Copy the structure from any page
4. Link from `blog.html`:
```html
<a href="blog/post-1.html">Read more →</a>
```

Example blog post structure:
```
your-repo/
├── index.html
├── blog.html              ← Blog listing
└── blog/
    ├── getting-started.html
    ├── ai-trends-2024.html
    └── rag-tutorial.html
```

### Updating Portfolio Projects

Edit `portfolio.html` and duplicate this section:
```html
<section class="content-section">
  <div class="grid-2">
    <div>
      <h2>Project Name</h2>
      <p>Description...</p>
      <h3>Results</h3>
      <ul>...</ul>
    </div>
    <div class="card">
      <!-- Project image or graphic -->
    </div>
  </div>
</section>
```

## 🔗 URL Structure & SEO

### Clean URLs (Optional)

To remove `.html` from URLs, you have two options:

**Option 1: Use folders (recommended)**
```
your-repo/
├── index.html
├── about/
│   └── index.html         → URL becomes /about/
├── services/
│   └── index.html         → URL becomes /services/
└── contact/
    └── index.html         → URL becomes /contact/
```

**Option 2: Keep .html extensions**
- Simpler to manage
- URLs like `/about.html` work fine
- Most users don't care

### SEO Checklist

✅ Each page has unique `<title>`
✅ Each page has unique meta description
✅ Logo has proper alt text
✅ All links have descriptive text
✅ Images have alt attributes
✅ Headings (h1, h2) are properly structured

### Adding Google Analytics

1. Get tracking ID from [analytics.google.com](https://analytics.google.com)
2. Add to **ALL HTML files** before `</head>`:
```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

## 🎯 Common Tasks

### Updating Contact Email

Search and replace in ALL files:
- Find: `sales@neurallabs.us`
- Replace: your actual email

### Adding a Privacy Policy

1. Create `privacy.html`
2. Add content about data collection
3. Link from footer in all files:
```html
<a href="privacy.html">Privacy Policy</a>
```

### Adding Testimonials

Add to `about.html` or create `testimonials.html`:
```html
<section class="content-section">
  <h2>What Clients Say</h2>
  <div class="grid-2">
    <div class="card">
      <p>"Neural Labs transformed our..."</p>
      <strong>— John Doe, CEO at TechCorp</strong>
    </div>
  </div>
</section>
```

### Creating a Sitemap

Create `sitemap.xml`:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://neurallabs.us/</loc>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://neurallabs.us/about.html</loc>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://neurallabs.us/services.html</loc>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://neurallabs.us/contact.html</loc>
    <priority>0.9</priority>
  </url>
</urlset>
```

## 🐛 Troubleshooting

### Pages not showing up?
- Check GitHub Actions tab for errors
- Ensure files are in root directory (not in a folder)
- Wait 2-3 minutes after uploading
- Clear browser cache (Ctrl+Shift+R)

### Links not working?
- Check file names match exactly (case-sensitive)
- Ensure all files have `.html` extension
- Verify logo path is correct in all files

### Styles not loading?
- Ensure `style.css` is in root directory
- Check that all HTML files link to it correctly
- Clear browser cache

### Forms not working?
- Verify Formspree form IDs are correct
- Check that you replaced `YOUR_FORM_ID`
- Test form submission and check Formspree dashboard

## 📱 Mobile Testing

Test your site on mobile:
1. Open on your phone: `https://neurallabs.us/`
2. Or use Chrome DevTools (F12) → Toggle device toolbar
3. Test all pages and navigation
4. Check forms work on mobile

## 🚀 Performance Tips

1. **Optimize images**: Use WebP format when possible
2. **Enable caching**: GitHub Pages does this automatically
3. **Minify CSS**: Use a tool like [CSS Minifier](https://www.toptal.com/developers/cssminifier)
4. **Monitor speed**: Use [PageSpeed Insights](https://pagespeed.web.dev/)

## 📊 Analytics & Tracking

### What to Track

- Page views for each page
- Contact form submissions
- Newsletter signups
- Time on site
- Bounce rate
- Traffic sources

### Tools to Use

- **Google Analytics**: Free, comprehensive
- **Formspree**: Form submission tracking (built-in)
- **Google Search Console**: SEO performance

## 🎉 You're Done!

Your multi-page website is now live at:
- https://neurallabs.us/ (Homepage)
- https://neurallabs.us/about.html
- https://neurallabs.us/services.html
- https://neurallabs.us/portfolio.html
- https://neurallabs.us/blog.html
- https://neurallabs.us/contact.html

## 📞 Next Steps

1. ✅ Set up Formspree forms
2. ✅ Update social media links
3. ✅ Test all pages on mobile
4. ✅ Enable Google Analytics
5. ✅ Create social media accounts
6. ✅ Start writing blog content
7. ✅ Add real portfolio projects
8. ✅ Get feedback from colleagues

## 🆘 Need Help?

Email: sales@neurallabs.us

---

**Made with ❤️ for Neural Labs**
