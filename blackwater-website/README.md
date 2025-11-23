# Blackwater Land Management LLC - Website

Complete total site work services website for East Texas land development.

## 🚀 Quick Start

This website is designed to be deployed via GitHub Pages with a custom domain.

### Prerequisites
- GitHub account
- Custom domain (configured)
- MailerLite account (for email marketing)
- Google Forms (for quote requests)

### Deployment to GitHub Pages

1. **Create GitHub Repository**
   ```bash
   # Initialize repository
   git init
   git add .
   git commit -m "Initial commit - Blackwater Land Management website"
   
   # Connect to GitHub
   git remote add origin https://github.com/YOUR-USERNAME/blackwater-land-management.git
   git branch -M main
   git push -u origin main
   ```

2. **Enable GitHub Pages**
   - Go to repository Settings
   - Navigate to "Pages" section
   - Source: Deploy from "main" branch
   - Folder: / (root)
   - Click Save

3. **Configure Custom Domain**
   - In GitHub Pages settings, add your custom domain
   - In your domain registrar (GoDaddy, Namecheap, etc.):
     - Add A records pointing to GitHub Pages IPs:
       ```
       185.199.108.153
       185.199.109.153
       185.199.110.153
       185.199.111.153
       ```
     - Add CNAME record: `www` pointing to `YOUR-USERNAME.github.io`
   - Check "Enforce HTTPS" in GitHub Pages settings

## 📁 Project Structure

```
blackwater-land-management/
├── index.html              # Homepage
├── services.html           # Services page
├── about.html             # About page
├── contact.html           # Contact/Quote page
├── css/
│   └── styles.css         # Main stylesheet
├── js/
│   └── main.js            # JavaScript functionality
├── images/
│   ├── logo.jpg           # Main logo
│   ├── logo-white.svg     # White logo for dark backgrounds
│   └── [project photos]   # Service and project images
├── favicon.ico            # Browser favicon
└── README.md             # This file
```

## 🎨 Brand Guidelines

### Colors
- **Primary Black:** `#000000` - Main text, headers
- **Burnt Orange:** `#D2691E` - CTAs, accents (from logo sunset)
- **White:** `#FFFFFF` - Backgrounds, contrast
- **Charcoal Gray:** `#333333` - Secondary text

### Typography
- **Headers:** Bold sans-serif (complementing logo)
- **Body:** Clean, readable sans-serif
- **Mobile-friendly:** Minimum 16px body text

### Logo Usage
- Full color on light backgrounds
- White version on dark sections (hero, footer)
- Logo always links to homepage

## 📧 MailerLite Integration

### Setup Instructions

1. **Create MailerLite Account** (if not already done)
   - Sign up at mailerlite.com
   - Verify email and complete setup

2. **Create a Group for Quote Requests**
   - Go to Subscribers → Groups
   - Create new group: "Quote Requests" or "Website Leads"

3. **Get Embedded Form Code**
   - Go to Forms → Create Form
   - Choose "Embedded form"
   - Customize fields to match quote form
   - Copy embed code

4. **Integration Options**

   **Option A: Replace Google Form with MailerLite Form**
   - Paste MailerLite embed code in `contact.html`
   - Replace the `<form id="quote-form">` section
   - MailerLite handles email delivery automatically

   **Option B: Keep Google Form + Add MailerLite**
   - Keep Google Form as primary
   - Add MailerLite signup form for newsletter/updates
   - Use Zapier to connect Google Forms → MailerLite
     - Trigger: New Google Form submission
     - Action: Add subscriber to MailerLite

5. **Email Automation Setup** (Optional but Recommended)
   - Create auto-response email: "Thanks for your quote request"
   - Set up notification to yourself for new leads
   - Configure follow-up sequence

## 📝 Google Forms Integration

### Setup Instructions

1. **Prepare Your Google Form**
   - Make sure form collects all necessary info:
     - Name
     - Phone
     - Email
     - Property Location
     - County
     - Services Needed
     - Timeline
     - Project Details
   - Enable email notifications (Settings → Responses → Get email notifications)

2. **Get Form Embed Code**
   - Click "Send" button in Google Forms
   - Click embed icon `< >`
   - Copy iframe code

3. **Add to Website**
   - Open `contact.html`
   - Find the `<form id="quote-form">` section
   - Replace with Google Forms iframe:
     ```html
     <iframe 
       src="YOUR_GOOGLE_FORM_EMBED_URL" 
       width="100%" 
       height="1200" 
       frameborder="0" 
       marginheight="0" 
       marginwidth="0">
       Loading…
     </iframe>
     ```

4. **Style the Embedded Form** (Optional)
   - Add CSS to match your site design
   - Google Forms has limited styling options
   - Consider using Google Form's theme settings first

### Alternative: Link to Google Form

Instead of embedding, you can link to the form:
```html
<a href="YOUR_GOOGLE_FORM_URL" class="btn-primary-large" target="_blank">
  Request Your Free Quote
</a>
```

## 📊 Analytics Setup

### Google Analytics 4

1. **Create GA4 Property**
   - Go to analytics.google.com
   - Create new property for your website
   - Copy Measurement ID (G-XXXXXXXXXX)

2. **Add to Website**
   - Add this code to `<head>` of all HTML files:
   ```html
   <!-- Google Analytics -->
   <script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
   <script>
     window.dataLayer = window.dataLayer || [];
     function gtag(){dataLayer.push(arguments);}
     gtag('js', new Date());
     gtag('config', 'G-XXXXXXXXXX');
   </script>
   ```

3. **Track Important Events**
   - Phone clicks
   - Form submissions
   - Service page views
   - Quote button clicks

### Google Business Profile Integration

1. **Claim/Verify Your Business**
   - Go to google.com/business
   - Claim Blackwater Land Management LLC
   - Complete verification process

2. **Add Website URL**
   - Link to your new custom domain
   - Add booking/quote link (contact page)

3. **Embed Reviews** (Optional)
   - Use Google Reviews widget
   - Display on homepage testimonials section

## 🔧 Required Updates Before Launch

### Content Updates

- [ ] Replace `[XXX-XXX-XXXX]` with actual phone number (all pages)
- [ ] Replace `[Email]` with business email (all pages)
- [ ] Add actual business address (if sharing publicly)
- [ ] Update "years in business" or "projects completed" stats
- [ ] Write actual customer testimonials (or collect from Google Reviews)
- [ ] Add team member names/info in About page (if desired)

### Image Updates

- [ ] Add hero background images (homepage)
- [ ] Add service-specific photos (services page)
- [ ] Add before/after project photos
- [ ] Create white version of logo for dark backgrounds
- [ ] Create favicon (512x512px square version of logo)
- [ ] Optimize all images (<200KB each)

### Form Updates

- [ ] Integrate Google Forms embed code OR
- [ ] Integrate MailerLite form code
- [ ] Test form submissions
- [ ] Set up email notifications
- [ ] Create auto-response email

### SEO Updates

- [ ] Add Google Analytics tracking code
- [ ] Submit sitemap to Google Search Console
- [ ] Verify custom domain in Search Console
- [ ] Add structured data markup (LocalBusiness schema)
- [ ] Create and submit robots.txt

## 📱 Mobile Optimization Checklist

- [ ] Test all pages on mobile devices
- [ ] Verify click-to-call phone links work
- [ ] Test form submission on mobile
- [ ] Confirm sticky CTA buttons appear/function
- [ ] Check image loading speeds
- [ ] Test navigation menu (hamburger)

## 🔍 SEO Checklist

- [ ] Unique title tags for each page
- [ ] Meta descriptions for each page
- [ ] Alt text for all images
- [ ] Heading hierarchy (H1, H2, H3)
- [ ] Internal linking between pages
- [ ] Custom domain with HTTPS
- [ ] Fast page load times (<3 seconds)
- [ ] Mobile-friendly design
- [ ] Submit to Google Search Console
- [ ] Submit to Bing Webmaster Tools

## 🚦 Pre-Launch Testing

### Functionality Tests
- [ ] All navigation links work
- [ ] Services dropdown menu functions
- [ ] Quote form submits successfully
- [ ] Phone click-to-call works
- [ ] Email links work
- [ ] External links (Facebook, Google) work
- [ ] Mobile sticky CTA appears after scroll

### Cross-Browser Tests
- [ ] Chrome
- [ ] Safari
- [ ] Firefox
- [ ] Edge
- [ ] Mobile Safari (iOS)
- [ ] Mobile Chrome (Android)

### Performance Tests
- [ ] Run Google PageSpeed Insights
- [ ] Run GTmetrix
- [ ] Test on slow 3G connection
- [ ] Verify images are compressed
- [ ] Check for broken links

## 🔐 Security

- [ ] HTTPS enabled (via GitHub Pages)
- [ ] Form spam protection (Google reCAPTCHA or honeypot)
- [ ] Privacy policy page (if collecting data)
- [ ] Secure email handling for form submissions

## 📞 Support & Maintenance

### Regular Updates
- Update project photos quarterly
- Add new customer testimonials
- Update service area if expanding
- Refresh pricing (if displayed)
- Add seasonal messaging

### Monitoring
- Check Google Analytics monthly
- Monitor form submissions
- Check for broken links quarterly
- Review Google Business Profile reviews

## 🛠️ Technical Support

### Common Issues

**GitHub Pages not loading custom domain:**
- Wait 24-48 hours for DNS propagation
- Verify DNS settings with your registrar
- Check HTTPS enforcement is enabled

**Form not submitting:**
- Check Google Forms URL is correct
- Verify iframe embed code is complete
- Test form directly on Google Forms first

**Mobile sticky CTA not appearing:**
- Clear browser cache
- Check JavaScript console for errors
- Verify main.js is loading

## 📞 Contact Information

**Business Phone:** [Your Phone Number]  
**Business Email:** [Your Email]  
**Website:** [Your Custom Domain]

## 📄 License

© 2024 Blackwater Land Management LLC. All rights reserved.

---

**Need help?** Contact your web developer or create an issue in this repository.
