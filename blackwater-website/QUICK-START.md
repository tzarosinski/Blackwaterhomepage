# QUICK START GUIDE - GET YOUR WEBSITE LIVE TODAY

This is your fast-track guide to getting Blackwater Land Management's website live and accepting quote requests.

## ⚡ WHAT YOU CAN DO RIGHT NOW (30 Minutes)

### Step 1: Get Files on GitHub (10 minutes)
1. Create GitHub account (if needed): github.com
2. Create new repository: "blackwater-land-management"
3. Upload all website files
4. Enable GitHub Pages in Settings → Pages
5. Your site is now live at: `https://YOUR-USERNAME.github.io/blackwater-land-management`

### Step 2: Add Your Contact Info (10 minutes)
Open each HTML file and replace:
- `[XXX-XXX-XXXX]` → Your actual phone number
- `[Email]` → Your actual email address

Save and push changes to GitHub.

### Step 3: Add Google Form (10 minutes)
1. Open your Google Form
2. Click "Send" → Embed `< >` icon
3. Copy the iframe code
4. Open `contact.html`
5. Find `<form id="quote-form">` section
6. Replace it with your Google Form iframe
7. Save and push to GitHub

**🎉 YOUR SITE IS NOW LIVE AND FUNCTIONAL!**

---

## 📅 WHAT TO DO IN THE NEXT 24-48 HOURS

### Connect Your Custom Domain
**In your domain registrar (GoDaddy, Namecheap, etc.):**

1. Add these A Records:
   ```
   Type: A | Host: @ | Value: 185.199.108.153
   Type: A | Host: @ | Value: 185.199.109.153
   Type: A | Host: @ | Value: 185.199.110.153
   Type: A | Host: @ | Value: 185.199.111.153
   ```

2. Add CNAME Record:
   ```
   Type: CNAME | Host: www | Value: YOUR-GITHUB-USERNAME.github.io
   ```

3. Save DNS settings

**In GitHub:**
1. Go to Settings → Pages
2. Add your custom domain
3. Wait for DNS check (up to 24 hours)
4. Enable "Enforce HTTPS"

---

## 🖼️ WHAT TO DO THIS WEEK

### Add Photos (Priority Order)
1. Hero background image (homepage)
2. Logo files (color + white version)
3. Favicon (square logo)
4. Service photos (septic, clearing, driveway, pad)
5. Before/after project photos

Upload to `/images/` folder and update HTML file references.

### Set Up MailerLite
1. Create account at mailerlite.com
2. Create group: "Website Leads"
3. Set up welcome automation
4. Connect via Zapier:
   - Trigger: Google Forms new response
   - Action: Add to MailerLite
   - Group: Website Leads

### Add Analytics
1. Create Google Analytics account
2. Get tracking code
3. Add to `<head>` of all HTML pages
4. Push to GitHub

---

## 📋 SIMPLE DAILY WORKFLOW

**Every Morning:**
1. Check email for Google Form notifications
2. Check MailerLite for new leads
3. Respond to quote requests within 24 hours

**Every Week:**
1. Check Google Analytics for traffic
2. Add new project photos
3. Ask satisfied customers for Google reviews

---

## 🎯 YOUR FIRST 30 DAYS

### Week 1: Launch
- [x] Get site live on GitHub Pages
- [ ] Connect custom domain
- [ ] Google Form working
- [ ] First test quote submission
- [ ] Announce on Facebook

### Week 2: Optimize
- [ ] All photos uploaded
- [ ] MailerLite connected
- [ ] Google Analytics running
- [ ] Google Business Profile updated
- [ ] First real quote request received

### Week 3: Promote
- [ ] Post to Facebook weekly
- [ ] Update Google Business Profile
- [ ] Add "Request Quote" buttons to Facebook
- [ ] Share website with Clayton Homes
- [ ] Ask for reviews from recent customers

### Week 4: Refine
- [ ] Review analytics data
- [ ] Add more project photos
- [ ] Update testimonials
- [ ] Consider adding blog or FAQ
- [ ] Plan next month's content

---

## 🚨 MUST-HAVE VS. NICE-TO-HAVE

### MUST HAVE (Do First)
✅ Phone number working
✅ Google Form receiving submissions
✅ Site live on custom domain
✅ At least 1 hero photo
✅ Logo displayed correctly

### NICE TO HAVE (Do Later)
⏳ Professional photography
⏳ Video content
⏳ Blog posts
⏳ Customer testimonials
⏳ Advanced analytics

---

## 💡 PRO TIPS

1. **Test Your Own Form Weekly** - Submit a fake quote request to make sure everything still works

2. **Respond Fast** - The faster you respond to quote requests, the higher your conversion rate

3. **Mobile First** - 70%+ of your traffic will be mobile. Test on your phone constantly.

4. **Keep It Simple** - Don't overthink it. A working website is better than a perfect website that's not live.

5. **Add Photos Gradually** - Start with 5 good photos. Add more each week as you complete projects.

6. **Monitor Your Inbox** - Set up Google Form notifications to go to your phone

---

## 🆘 QUICK FIXES

**Form not working?**
→ Test it directly on Google Forms first, then check embed code

**Domain not connecting?**
→ Wait 24-48 hours, DNS takes time

**Not getting notifications?**
→ Check spam folder, verify email in Google Forms settings

**Site looks broken on mobile?**
→ Clear cache, try incognito mode

---

## 📞 TECHNICAL SUPPORT RESOURCES

- **GitHub Pages:** docs.github.com/pages
- **Google Forms:** support.google.com/forms
- **MailerLite:** mailerlite.com/help
- **DNS Setup:** Your domain registrar's help docs

---

## ✅ MINIMUM VIABLE LAUNCH CHECKLIST

Before you share your website publicly, make sure:

- [ ] Your phone number is correct on every page
- [ ] Quote form submits successfully
- [ ] You receive email notifications
- [ ] Site loads on your custom domain
- [ ] At least homepage has a background image
- [ ] Logo displays correctly
- [ ] You've tested on your mobile phone
- [ ] All navigation links work

**That's it! If these 8 things work, you're ready to launch.** 🚀

Everything else can be improved over time.

---

## 🎯 FOCUS ON THIS

Your goal is simple: **Get quote requests from potential customers.**

Everything else is secondary. Don't get stuck on:
- Perfect photos
- Perfect copy
- Advanced features
- Complex integrations

Get it live. Get it working. Get quote requests. Improve as you go.

**Launch today. Perfect tomorrow.**
