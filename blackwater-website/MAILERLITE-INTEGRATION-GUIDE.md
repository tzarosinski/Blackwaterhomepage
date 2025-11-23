# MAILERLITE + GOOGLE FORMS INTEGRATION GUIDE

Complete guide to connecting your Google Forms quote requests to MailerLite for automated email marketing and lead nurturing.

---

## 🎯 WHY CONNECT MAILERLITE?

**What This Gives You:**
1. ✅ Automatic welcome emails to quote requesters
2. ✅ Build your email list while collecting quotes
3. ✅ Follow-up sequences for leads who don't respond
4. ✅ Organize contacts by project type or location
5. ✅ Professional email marketing (newsletters, updates, promotions)
6. ✅ Analytics on email performance

**What You Keep:**
- ✅ Your Google Form (no changes needed)
- ✅ Google Sheets responses
- ✅ Email notifications you're already getting

**This is an ADD-ON, not a replacement.**

---

## 🔧 METHOD 1: ZAPIER INTEGRATION (Recommended)

**Best For:** Keeping Google Forms while adding MailerLite automation

### What You Need
- Google Forms quote form (you have this ✅)
- MailerLite account (free up to 1,000 subscribers)
- Zapier account (free tier works fine)

### Step-by-Step Setup

#### PART A: Set Up MailerLite (15 minutes)

**1. Create MailerLite Account**
- Go to: mailerlite.com
- Click "Start Free" (no credit card needed)
- Sign up with your business email
- Verify email address
- Complete basic setup

**2. Create Your First Group**
- Log into MailerLite dashboard
- Click "Subscribers" in left menu
- Click "Groups" tab
- Click "Create Group"
- Name it: **"Website Quote Requests"**
- Click "Create"

**3. Set Up Custom Fields** (Important!)
These will store info from your Google Form:
- Click "Subscribers" → "Fields"
- Click "Create Field"
- Create these fields:

| Field Name | Field Type |
|------------|------------|
| Phone | Text |
| Property Location | Text |
| County | Text |
| Services Needed | Text |
| Project Timeline | Text |
| Project Details | Text |

- Save each field

**4. Create Welcome Automation**
- Click "Automations" in left menu
- Click "Create Automation"
- Choose "Start from scratch"
- Name it: "Quote Request Welcome Email"
- Trigger: "Joins a group" → Select "Website Quote Requests"
- Click "Add step" → "Send email"
- Create your email:

**Subject Line:** Thanks for contacting Blackwater Land Management!

**Email Body Example:**
```
Hi {$name},

Thanks for requesting a quote from Blackwater Land Management!

We've received your information and will contact you within 24 hours to discuss 
your total site work project.

Here's what you requested:
• Services: {$services_needed}
• Location: {$property_location}
• County: {$county}

In the meantime, feel free to call us directly at [YOUR PHONE NUMBER] if you 
have any questions.

Best regards,
Blackwater Land Management
[YOUR PHONE NUMBER]
[YOUR EMAIL]

---
Tyler, TX | Complete Total Site Work Services
Septic Systems | Land Clearing | House Pads | Driveways
```

- Click "Save"
- Toggle automation to "Active"
- Click "Done"

#### PART B: Set Up Zapier Connection (10 minutes)

**1. Create Zapier Account**
- Go to: zapier.com
- Sign up (free tier is perfect for this)
- Verify email

**2. Create Your Zap**
- Click "Create Zap"
- Name it: "Google Forms → MailerLite"

**3. Set Up Trigger (Google Forms)**
- Search for "Google Forms"
- Choose "New Response in Spreadsheet"
- Click "Continue"
- Click "Sign in to Google Forms"
- Allow Zapier access
- Choose your Quote Request form
- Click "Continue"
- Click "Test trigger"
- Select a test response (or submit one if needed)
- Click "Continue"

**4. Set Up Action (MailerLite)**
- Search for "MailerLite"
- Choose "Create/Update Subscriber"
- Click "Continue"
- Click "Sign in to MailerLite"
- Copy API key from MailerLite (Settings → Integrations → API)
- Paste into Zapier
- Click "Continue"

**5. Map Your Fields**
This is where you connect Google Form answers to MailerLite fields:

| MailerLite Field | Maps to Google Form Column |
|------------------|----------------------------|
| Email | Email Address |
| Name | Full Name |
| Phone (custom field) | Phone Number |
| Property Location (custom field) | Property Address/Location |
| County (custom field) | County |
| Services Needed (custom field) | Services Needed |
| Project Timeline (custom field) | Project Timeline |
| Project Details (custom field) | Project Details |

- Select Group: "Website Quote Requests"
- Resubscribe: "Yes" (in case they submitted before)
- Click "Continue"

**6. Test Your Zap**
- Click "Test & Continue"
- Check MailerLite to see if test subscriber appeared
- Check if welcome email was sent
- If everything works, click "Publish Zap"

**7. Turn It On**
- Toggle Zap to "On"
- You're done! 🎉

---

## 🧪 TESTING YOUR SETUP

**Complete Test Workflow:**

1. **Submit Test Quote**
   - Go to your website
   - Fill out quote form with test data
   - Use your own email address
   - Submit

2. **Check Google Forms**
   - Log into Google Forms
   - Verify response recorded
   - Check that you got email notification

3. **Check MailerLite**
   - Log into MailerLite
   - Go to Subscribers
   - Look for your test email
   - Verify it's in "Website Quote Requests" group
   - Check that all custom fields populated

4. **Check Your Email**
   - Look for welcome email from MailerLite
   - Verify it looks correct
   - Check all merge fields worked ({$name}, etc.)

5. **Fix Issues**
   - If fields didn't populate: Check Zapier field mapping
   - If no email arrived: Check spam, verify automation is active
   - If subscriber didn't appear: Check Zapier task history for errors

---

## 📧 ADVANCED EMAIL AUTOMATIONS (Optional)

Once basic setup works, add these automations:

### 1. Follow-Up Sequence
For leads who don't respond to first contact:

**Day 3 Email:**
```
Subject: Following up on your quote request

Hi {$name},

I wanted to follow up on the quote request you submitted for total site work 
in {$county} County.

Have you had a chance to review our initial response? I'm happy to answer any 
questions about:
• Septic system installation
• Land clearing and site prep
• Timeline and pricing
• Our process

Give me a call at [YOUR PHONE] or reply to this email.

Best,
[Your Name]
Blackwater Land Management
```

**Day 7 Email:**
```
Subject: Last chance - Your quote expires soon

Hi {$name},

I know life gets busy, and choosing a contractor for total site work is a big 
decision.

Our quote for your project in {$county} County is still available, but I wanted 
to reach out one last time before we close out your request.

If you're still interested or have questions, I'm here to help.

Call: [YOUR PHONE]
Email: [YOUR EMAIL]

Thanks,
[Your Name]
```

**Setup in MailerLite:**
- Automations → Create Automation
- Trigger: "Joins group: Website Quote Requests"
- Wait: 3 days → Send Email (Day 3)
- Wait: 4 days → Send Email (Day 7)
- Done!

### 2. Monthly Newsletter
Keep past leads warm:
- Create email campaign
- Send to "Website Quote Requests" group
- Content ideas:
  - Recent projects (before/after)
  - Seasonal tips (spring clearing, winter prep)
  - Special promotions
  - Customer testimonials
  - Service area updates

### 3. Re-engagement Campaign
For old leads (6+ months):
```
Subject: Still need site work? We're here to help

Hi {$name},

You reached out to Blackwater Land Management about {$services_needed} back in 
{$project_timeline}.

If your plans changed or you're ready to move forward now, we'd love to help 
with your total site work project in {$county} County.

New this year:
• Expanded service area
• Updated equipment
• Even faster turnaround times

Get a fresh quote: [LINK TO CONTACT PAGE]

Best,
[Your Name]
```

---

## 📊 USING MAILERLITE DATA

### Segment Your List

Create segments for targeted messaging:

**By Service Type:**
- Subscribers with "Septic" in Services Needed
- Subscribers with "Land Clearing" in Services Needed
- Subscribers with "Mobile Home" in Project Details

**By Location:**
- Smith County residents
- Cherokee County residents
- Etc.

**By Timeline:**
- ASAP projects (send different message)
- Just Planning (nurture sequence)

**How to Create Segments:**
- MailerLite → Subscribers → Segments
- Create New Segment
- Add conditions based on custom fields
- Save

### Track Performance

**In MailerLite Dashboard:**
- Open rates (aim for 20%+)
- Click rates (aim for 3%+)
- Unsubscribe rates (keep under 0.5%)
- Campaign performance

**Monthly Review:**
- How many quote requests → MailerLite?
- How many opened welcome email?
- How many clicked through to site?
- Which emails get best engagement?

---

## 🔒 PRIVACY & COMPLIANCE

### GDPR/Privacy Considerations

**Add to Your Quote Form:**
```
☐ I agree to receive emails from Blackwater Land Management about my quote 
request and occasional updates about site work services. You can unsubscribe 
anytime.
```

**Add to Website Footer:**
- Link to Privacy Policy
- Example: "We respect your privacy. Read our [Privacy Policy]"

**In MailerLite Emails:**
- Unsubscribe link (MailerLite adds automatically)
- Physical address (MailerLite adds automatically)
- Clear sender information

### Best Practices
- Only email people who requested quotes
- Make it easy to unsubscribe
- Don't spam (1-2 emails/week max)
- Respect unsubscribe requests immediately
- Keep customer data secure

---

## 💰 MAILERLITE PRICING

**Free Plan:**
- Up to 1,000 subscribers
- 12,000 emails/month
- All features included
- Perfect for getting started

**When to Upgrade:**
- You'll know when you hit 1,000 subscribers
- Growing Business plan: $9-15/month (1,000-2,500 subscribers)
- Advanced features: A/B testing, dynamic content

**Typical Growth Timeline:**
- Month 1-3: Stay on free plan
- Month 6: Maybe 100-200 subscribers
- Year 1: Possibly 500-1,000 subscribers
- Year 2: Consider paid plan

---

## 🆘 TROUBLESHOOTING

### "Zapier isn't triggering"
- Check Zap is turned "On"
- Verify Google Forms is collecting responses
- Check Zapier Task History for errors
- Try submitting a new test form

### "Subscriber appears in MailerLite but no welcome email"
- Check automation is "Active"
- Verify trigger is set to correct group
- Check subscriber's email isn't bounced/invalid
- Look in spam folder

### "Custom fields aren't populating"
- Check field names match exactly in MailerLite
- Verify Zapier field mapping
- Check Google Forms column names
- Re-test Zap

### "Getting 'Invalid API Key' error"
- Get fresh API key from MailerLite
- Settings → Integrations → Developer API
- Copy and paste carefully (no extra spaces)
- Re-authorize in Zapier

### "Emails going to spam"
- Add your domain to MailerLite
- Verify domain with SPF/DKIM records
- Ask recipients to add you to contacts
- Avoid spam trigger words ("free", "urgent", etc.)

---

## 📋 MAILERLITE QUICK REFERENCE

### Dashboard Overview
- **Campaigns:** Send one-time emails
- **Automations:** Triggered email sequences
- **Subscribers:** View/manage your list
- **Forms:** Create embedded forms (optional)
- **Sites:** Landing pages (optional)
- **Reports:** Analytics and performance

### Key Actions
- **Send broadcast:** Campaigns → Create Campaign
- **Edit automation:** Automations → Edit
- **Add subscriber manually:** Subscribers → Add Subscriber
- **Create segment:** Subscribers → Segments → Create
- **Check stats:** Reports → Overview

### Support Resources
- Help docs: mailerlite.com/help
- Video tutorials: youtube.com/mailerlite
- Email support: support@mailerlite.com
- Live chat (free plan has it!)

---

## ✅ MAILERLITE SETUP CHECKLIST

**Initial Setup:**
- [ ] MailerLite account created
- [ ] Email verified
- [ ] "Website Quote Requests" group created
- [ ] Custom fields created (Phone, Location, County, Services, Timeline, Details)
- [ ] Welcome automation created and active
- [ ] Zapier account created
- [ ] Zap created: Google Forms → MailerLite
- [ ] Field mapping completed
- [ ] Test quote submitted
- [ ] Test subscriber appeared in MailerLite
- [ ] Welcome email received
- [ ] Zap turned on

**Optional But Recommended:**
- [ ] Follow-up sequence created
- [ ] Monthly newsletter template created
- [ ] Segments created for targeting
- [ ] Domain verified in MailerLite
- [ ] Privacy policy added to website
- [ ] Opt-in language added to form

---

## 🎯 NEXT STEPS AFTER SETUP

1. **Week 1:** Just monitor. Make sure everything works.
2. **Week 2:** Review first subscribers, tweak welcome email if needed
3. **Week 3:** Create first newsletter or update email
4. **Month 2:** Add follow-up sequence
5. **Month 3:** Start segmenting and targeting
6. **Ongoing:** Monthly newsletters, seasonal promotions

---

**Remember:** MailerLite is a tool to help you stay in touch with leads and convert more quotes into customers. Start simple, then add complexity as you get comfortable.

**Questions?** MailerLite support is excellent. Use their live chat!
