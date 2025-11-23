# BLACKWATER LAND MANAGEMENT WEBSITE - DEPLOYMENT CHECKLIST

## 🎯 CRITICAL PATH TO LAUNCH

Complete these items in order to get your website live and functional for quote requests.

---

## PHASE 1: GITHUB & DOMAIN SETUP (Day 1)

### GitHub Repository Setup
- [ ] Create new GitHub repository named "blackwater-land-management"
- [ ] Upload all website files to repository
- [ ] Commit with message: "Initial website deployment"
- [ ] Push to main branch

### Enable GitHub Pages
- [ ] Go to repository Settings → Pages
- [ ] Select Source: "Deploy from a branch"
- [ ] Branch: "main" 
- [ ] Folder: "/ (root)"
- [ ] Click "Save"
- [ ] Note the GitHub Pages URL (https://YOUR-USERNAME.github.io/blackwater-land-management)

### Custom Domain Configuration
**In GitHub:**
- [ ] Go to Settings → Pages → Custom domain
- [ ] Enter your custom domain (example: blackwaterlandmanagement.com)
- [ ] Click "Save"
- [ ] Wait for DNS check (may take up to 24 hours)

**In Your Domain Registrar (GoDaddy, Namecheap, etc.):**
- [ ] Log into domain registrar account
- [ ] Navigate to DNS settings for your domain
- [ ] Add A Records (create 4 separate A records):
  ```
  Type: A | Host: @ | Value: 185.199.108.153
  Type: A | Host: @ | Value: 185.199.109.153
  Type: A | Host: @ | Value: 185.199.110.153
  Type: A | Host: @ | Value: 185.199.111.153
  ```
- [ ] Add CNAME Record:
  ```
  Type: CNAME | Host: www | Value: YOUR-GITHUB-USERNAME.github.io
  ```
- [ ] Save DNS changes
- [ ] Wait 24-48 hours for DNS propagation

**Back in GitHub Pages Settings:**
- [ ] Once DNS check passes, check "Enforce HTTPS"
- [ ] Verify site loads at your custom domain

---

## PHASE 2: CONTENT UPDATES (Day 1-2)

### Contact Information (Global - All Pages)
- [ ] Replace all `[XXX-XXX-XXXX]` with: **YOUR PHONE NUMBER**
- [ ] Replace all `[Email]` with: **YOUR EMAIL ADDRESS**
- [ ] Update business hours if different from defaults
- [ ] Add physical address (if sharing publicly) or use "Serving East Texas"

### Homepage Updates
- [ ] Add actual customer testimonials (or pull from Google Reviews)
- [ ] Update "years in business" stat (or remove if not applicable)
- [ ] Update "projects completed" stat (or remove if not applicable)
- [ ] Verify service area counties are correct

### About Page Updates
- [ ] Write "Our Story" section (or use provided template)
- [ ] Add team member info (Hayden's background, your role)
- [ ] Add any relevant certifications or licenses
- [ ] Confirm partnership mentions (Clayton Homes, etc.)

### Services Page Updates
- [ ] Review all service descriptions
- [ ] Add any additional services not listed
- [ ] Verify pricing approach (quote-based vs. listed)
- [ ] Confirm package offerings match what you actually offer

### Contact Page Updates
- [ ] Verify all form fields match your needs
- [ ] Update FAQ answers if needed
- [ ] Confirm response time commitment (24 hours)

---

## PHASE 3: GOOGLE FORMS INTEGRATION (Day 2)

### Prepare Google Form
- [ ] Open your existing Google Form
- [ ] Verify all these fields are included:
  - Full Name
  - Phone Number
  - Email Address
  - Property Location/Address
  - County (dropdown with your 8 counties)
  - Services Needed (checkboxes)
  - Project Timeline
  - Project Details (text area)
  - Optional: "Working with mobile home dealer?" checkbox
- [ ] Go to Settings (gear icon)
- [ ] Enable "Collect email addresses"
- [ ] Enable "Get email notification for each new response"
- [ ] Add your email for notifications

### Get Embed Code
- [ ] In Google Form, click "Send" button (top right)
- [ ] Click the embed icon `< >` 
- [ ] Copy the iframe code (looks like `<iframe src="https://docs.google.com/forms/d/e/...`)
- [ ] Adjust height if needed (suggest 1800-2200px for your fields)

### Add to Contact Page
- [ ] Open `contact.html` file
- [ ] Find the `<form id="quote-form">` section (around line 50-150)
- [ ] Replace entire form section with your Google Forms iframe
- [ ] Example:
  ```html
  <div class="quote-form-container">
    <h2>Request Your Free Quote</h2>
    <p>Fill out the form below and we'll get back to you within 24 hours.</p>
    
    <iframe 
      src="YOUR_GOOGLE_FORM_EMBED_URL_HERE"
      width="100%" 
      height="2000" 
      frameborder="0" 
      marginheight="0" 
      marginwidth="0">
      Loading…
    </iframe>
  </div>
  ```
- [ ] Save and commit changes
- [ ] Push to GitHub
- [ ] Test form on live site

### Test Google Form
- [ ] Submit a test quote request through website
- [ ] Verify you receive email notification
- [ ] Check that response is recorded in Google Sheets
- [ ] Verify auto-response email is sent (if configured)
- [ ] Test from mobile device

---

## PHASE 4: MAILERLITE SETUP (Day 2-3)

### Create MailerLite Account
- [ ] Sign up at mailerlite.com (free for up to 1,000 subscribers)
- [ ] Verify email address
- [ ] Complete account setup

### Create Subscriber Group
- [ ] Go to Subscribers → Groups
- [ ] Click "Create Group"
- [ ] Name it "Website Leads" or "Quote Requests"
- [ ] Save group

### Set Up Welcome Email
- [ ] Go to Automations
- [ ] Create new automation: "Welcome to Blackwater"
- [ ] Trigger: "Subscriber joins group: Website Leads"
- [ ] Action: Send email with subject "Thanks for your quote request!"
- [ ] Email content:
  ```
  Hi {$name},
  
  Thanks for requesting a quote from Blackwater Land Management!
  
  We've received your information and will contact you within 24 hours 
  to discuss your total site work project.
  
  In the meantime, feel free to call us directly at [YOUR PHONE] if 
  you have any questions.
  
  Best regards,
  Blackwater Land Management
  [YOUR PHONE]
  ```
- [ ] Enable automation

### Connect to Website (Choose One Method)

**METHOD A: Zapier Integration (Recommended - Keeps Google Form)**
- [ ] Sign up for Zapier account (free tier works)
- [ ] Create new Zap
- [ ] Trigger: Google Forms → New Response
- [ ] Connect your Google account and select your form
- [ ] Action: MailerLite → Create/Update Subscriber
- [ ] Connect MailerLite account
- [ ] Map fields:
  - Name → Name
  - Email → Email
  - Phone → Phone (custom field)
  - Other details → Custom fields as needed
- [ ] Add subscriber to "Website Leads" group
- [ ] Test Zap
- [ ] Turn Zap on

**METHOD B: MailerLite Form (Replaces Google Form)**
- [ ] In MailerLite, go to Forms → Create Form
- [ ] Choose "Embedded form"
- [ ] Add fields to match your Google Form
- [ ] Customize design to match website colors
- [ ] Copy embed code
- [ ] Replace Google Form in `contact.html` with MailerLite code
- [ ] Test submission

### Set Up Lead Notifications (For You)
- [ ] In MailerLite, go to Automations
- [ ] Create automation: "New Lead Notification"
- [ ] Trigger: "Subscriber joins group: Website Leads"
- [ ] Action: Send email to YOUR email
- [ ] Email subject: "New Quote Request - Blackwater"
- [ ] Email includes: Name, Phone, Email, Project details
- [ ] Enable automation

---

## PHASE 5: IMAGES & MEDIA (Day 3-4)

### Logo Files
- [ ] Upload current logo to `/images/logo.jpg`
- [ ] Create white version for dark backgrounds → `/images/logo-white.svg` or `.png`
- [ ] Create favicon (square version, 512x512px) → `/favicon.ico`
- [ ] Update all logo references in HTML files

### Project Photos Needed
**Priority 1 - Must Have:**
- [ ] 1 hero background image (equipment working or completed site)
- [ ] 1 septic installation photo
- [ ] 1 land clearing photo
- [ ] 1 completed house pad photo
- [ ] 1 driveway photo

**Priority 2 - Should Have:**
- [ ] 3-5 before/after comparison sets
- [ ] Culvert installation photo
- [ ] Trenching work photo
- [ ] Mobile home on completed pad
- [ ] Team/equipment photo for About page

**Priority 3 - Nice to Have:**
- [ ] Additional service photos
- [ ] Multiple hero background options
- [ ] Customer site photos (with permission)
- [ ] Video clips for social media

### Image Optimization
- [ ] Compress all images to <200KB (use tinypng.com or similar)
- [ ] Convert to WebP format (optional but recommended)
- [ ] Add descriptive filenames (septic-installation.jpg not IMG_1234.jpg)
- [ ] Upload to `/images/` folder
- [ ] Update image src in HTML files
- [ ] Add alt text to all images for SEO

### Update Image References
- [ ] Homepage hero background
- [ ] Services page service icons/photos
- [ ] About page team/equipment photos
- [ ] Testimonials section (optional customer photos)
- [ ] Update alt text for all images

---

## PHASE 6: SEO & ANALYTICS (Day 4-5)

### Google Analytics Setup
- [ ] Create Google Analytics 4 account at analytics.google.com
- [ ] Create new property for your website
- [ ] Copy Measurement ID (format: G-XXXXXXXXXX)
- [ ] Add tracking code to `<head>` section of ALL HTML files:
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
- [ ] Commit and push changes
- [ ] Verify tracking is working (visit site, check Real-Time reports in GA)

### Google Search Console
- [ ] Go to search.google.com/search-console
- [ ] Add your property (custom domain)
- [ ] Verify ownership (via DNS TXT record or HTML file upload)
- [ ] Submit sitemap (create sitemap.xml first if needed)
- [ ] Request indexing for main pages

### Google Business Profile
- [ ] Claim/verify Blackwater Land Management LLC on Google
- [ ] Add website URL (your custom domain)
- [ ] Add "/contact" as appointment/quote booking URL
- [ ] Upload photos from your image library
- [ ] Complete all business information
- [ ] Enable messaging if desired

### Meta Tags Verification
- [ ] Homepage has unique title and description
- [ ] Services page has unique title and description
- [ ] About page has unique title and description
- [ ] Contact page has unique title and description
- [ ] All images have alt text

---

## PHASE 7: TESTING (Day 5)

### Functionality Testing
- [ ] Click every navigation link (all pages)
- [ ] Test services dropdown menu (desktop)
- [ ] Test mobile hamburger menu
- [ ] Submit test quote through form
- [ ] Verify quote submission email arrives
- [ ] Click all CTA buttons (Request Quote, Call Now)
- [ ] Test click-to-call phone links on mobile
- [ ] Test email mailto links
- [ ] Verify sticky mobile CTA appears when scrolling
- [ ] Test all external links (Facebook, Google Business)

### Cross-Device Testing
**Desktop:**
- [ ] Chrome browser
- [ ] Safari browser
- [ ] Firefox browser
- [ ] Edge browser

**Mobile:**
- [ ] iPhone Safari
- [ ] Android Chrome
- [ ] Tablet (iPad/Android)

### Performance Testing
- [ ] Run Google PageSpeed Insights (pagespeed.web.dev)
  - Target: 90+ on mobile and desktop
- [ ] Run GTmetrix (gtmetrix.com)
  - Target: A grade
- [ ] Test on slow 3G connection (Chrome DevTools)
- [ ] Verify images load quickly
- [ ] Check total page size (<2MB per page)

### SEO Testing
- [ ] Run site:yourdomain.com search in Google
- [ ] Verify pages are being indexed
- [ ] Check mobile-friendly test (search.google.com/test/mobile-friendly)
- [ ] Verify schema markup (schema.org validator)

---

## PHASE 8: SOCIAL MEDIA & INTEGRATIONS (Day 5-6)

### Facebook Business Page
- [ ] Link website URL in Facebook page info
- [ ] Add custom button: "Request Quote" → link to /contact page
- [ ] Update cover photo with website hero image
- [ ] Post announcement about new website
- [ ] Enable messaging (connects to MailerLite eventually)

### Google Business Profile Posts
- [ ] Create first post: "New website launched!"
- [ ] Link to website
- [ ] Add photos from site
- [ ] Add "Get Quote" CTA

### Social Media Links
- [ ] Add Facebook page URL to website footer
- [ ] Add Google Business Profile URL to website footer
- [ ] Verify all social links work

---

## PHASE 9: FINAL PRE-LAUNCH CHECKLIST

### Content Review
- [ ] Proofread all pages for typos
- [ ] Verify all phone numbers are correct
- [ ] Verify all email addresses are correct
- [ ] Check that service area is accurate
- [ ] Review pricing strategy (quote-based vs. listed)
- [ ] Confirm all claims are accurate (certifications, partnerships)

### Legal & Compliance
- [ ] Privacy policy page (if collecting data via forms) - RECOMMENDED
- [ ] Terms of service (optional)
- [ ] Copyright notice in footer
- [ ] Verify business name/LLC status is correct

### Backup & Security
- [ ] HTTPS is enabled (via GitHub Pages)
- [ ] All form submissions are being received
- [ ] Email notifications are working
- [ ] No broken links (use broken link checker tool)

---

## PHASE 10: LAUNCH! 🚀

### Go Live
- [ ] Do final test quote submission
- [ ] Verify form → email → MailerLite workflow works
- [ ] Check site loads at custom domain
- [ ] Check site loads at www.yourdomain.com
- [ ] Announce on Facebook Business Page
- [ ] Update Google Business Profile with website
- [ ] Tell Clayton Homes about new website

### Post-Launch (Week 1)
- [ ] Monitor form submissions daily
- [ ] Check Google Analytics traffic
- [ ] Respond to all quote requests within 24 hours
- [ ] Check for any broken links or errors
- [ ] Get feedback from friends/family
- [ ] Ask first customers to leave Google reviews

---

## ONGOING MAINTENANCE CHECKLIST

### Weekly
- [ ] Check for new quote requests
- [ ] Review Google Analytics traffic
- [ ] Respond to any contact form submissions
- [ ] Check Google Business Profile messages

### Monthly
- [ ] Add new project photos to gallery
- [ ] Update testimonials with recent reviews
- [ ] Review Google Analytics for trends
- [ ] Check for broken links
- [ ] Update any seasonal messaging

### Quarterly
- [ ] Refresh homepage hero image
- [ ] Add new case studies or projects
- [ ] Review and update service descriptions
- [ ] Check competitor websites for new ideas
- [ ] Update meta descriptions if needed

### Annually
- [ ] Review all content for accuracy
- [ ] Update copyright year in footer
- [ ] Refresh all photos
- [ ] Review pricing strategy
- [ ] Consider adding new pages (blog, FAQ)

---

## 🆘 TROUBLESHOOTING GUIDE

### "My custom domain isn't working"
- Wait 24-48 hours for DNS propagation
- Check DNS settings with your registrar
- Verify A records and CNAME are correct
- Try accessing without "www" (yourdomain.com)
- Clear browser cache

### "Quote form isn't submitting"
- Check Google Form URL is correct in iframe
- Test the form directly on Google Forms
- Check browser console for JavaScript errors
- Verify iframe height is sufficient (increase if form is cut off)
- Try different browser

### "I'm not receiving email notifications"
- Check Google Forms settings → Response notifications are ON
- Check spam/junk folder
- Verify email address is correct in Google Forms settings
- Test with a different email address

### "MailerLite automation isn't triggering"
- Check automation is enabled
- Verify subscriber was added to correct group
- Check automation trigger settings
- Look in MailerLite logs for errors
- Test with a new subscriber

### "Mobile sticky CTA isn't showing"
- Clear browser cache
- Check that JavaScript is enabled
- Test in incognito/private mode
- Check browser console for errors
- Verify main.js file is loading

---

## 📞 NEED HELP?

**Technical Issues:**
- GitHub Pages documentation: docs.github.com/pages
- MailerLite support: mailerlite.com/help
- Google Forms help: support.google.com/forms

**Web Development Questions:**
- Create issue in GitHub repository
- Search Stack Overflow
- Contact a web developer

---

## ✅ LAUNCH SIGN-OFF

When you've completed all items above, sign off here:

- [ ] All content is accurate and proofread
- [ ] Google Forms integration is working
- [ ] MailerLite is receiving new leads
- [ ] All images are uploaded and optimized
- [ ] Analytics is tracking visitors
- [ ] Site loads on custom domain with HTTPS
- [ ] Mobile experience is tested and working
- [ ] Quote requests are being received and responded to

**Launch Date:** _______________

**Launched By:** _______________

**Notes:**
_______________________________________________________
_______________________________________________________
_______________________________________________________

---

🎉 **CONGRATULATIONS ON YOUR LAUNCH!** 🎉

Your professional website is now live and ready to generate quote requests for Blackwater Land Management!
