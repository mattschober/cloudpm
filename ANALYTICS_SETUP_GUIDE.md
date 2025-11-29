# Analytics & Tracking Setup Guide

This guide will help you configure all analytics and tracking tools for your website. All tools mentioned below are **FREE** to use.

## Overview

Your website now has the following tracking capabilities:
1. **Google Analytics 4 (GA4)** - Already configured ✅
2. **Cookiebot Consent Banner** - Requires setup
3. **Microsoft Clarity** - Requires setup
4. **LinkedIn Insight Tag** - Optional (recommended if active on LinkedIn)

---

## 1. Cookiebot Setup (FREE - 10 minutes)

Cookiebot provides GDPR/CCPA-compliant cookie consent management. The free tier supports up to **500 page views/month**.

### Steps:

1. **Sign up for free account**
   - Go to: https://www.cookiebot.com/en/try-for-free/
   - Enter your email and create an account
   - Select "Free" plan (no credit card required)

2. **Add your domain**
   - After signing up, you'll be asked to add your domain
   - Enter: `mattschober-cloudpm.com`
   - Follow the wizard to scan your website

3. **Get your Cookiebot ID**
   - After domain setup, you'll see your "Domain Group ID"
   - It looks like: `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`

4. **Update your HTML files**
   - Open each file: `index.html`, `desktop.html`, `mobile.html`
   - Find the line: `data-cbid="YOUR-COOKIEBOT-ID-HERE"`
   - Replace `YOUR-COOKIEBOT-ID-HERE` with your actual Cookiebot ID

5. **Test the banner**
   - Visit your website
   - You should see a cookie consent banner at the bottom
   - Test accepting/rejecting cookies to verify it works

### What Cookiebot Does:
- Displays a cookie consent banner to visitors
- Automatically blocks GA4, Clarity, and LinkedIn tracking until consent is given
- Provides a cookie declaration page
- Ensures GDPR/CCPA compliance

---

## 2. Microsoft Clarity Setup (FREE - 5 minutes)

Microsoft Clarity provides heatmaps, session recordings, and user behavior analytics. Completely free with unlimited traffic.

### Steps:

1. **Sign up for Clarity**
   - Go to: https://clarity.microsoft.com/
   - Click "Sign up" (can use existing Microsoft account)

2. **Create a new project**
   - Click "+ New Project"
   - Project name: `Matt Schober CloudPM`
   - Website URL: `https://mattschober-cloudpm.com`
   - Category: `Professional Services` or `Consulting`

3. **Get your Clarity Project ID**
   - After creating project, go to "Setup" tab
   - Look for "Project ID" - it looks like: `abcd1234ef`
   - Copy this ID

4. **Update your HTML files**
   - Open each file: `index.html`, `desktop.html`, `mobile.html`
   - Find the line: `"YOUR-CLARITY-ID-HERE"`
   - Replace `YOUR-CLARITY-ID-HERE` with your actual Clarity Project ID

5. **Verify installation**
   - Go back to Clarity dashboard
   - Within a few minutes, you should see "Setup successful" status
   - Visit your website to generate test data

### What Clarity Provides:
- **Heatmaps**: See where users click, scroll, and hover
- **Session Recordings**: Watch real user sessions (privacy-safe)
- **Insights Dashboard**: Automatic detection of user frustration, rage clicks, etc.
- **No traffic limits**: Unlimited page views and recordings

---

## 3. LinkedIn Insight Tag (Optional - 10 minutes)

If you're active on LinkedIn and running LinkedIn ads or want conversion tracking, set this up.

### Steps:

1. **Access LinkedIn Campaign Manager**
   - Go to: https://www.linkedin.com/campaignmanager
   - Sign in with your LinkedIn account
   - You may need to create a Campaign Manager account (free)

2. **Create Insight Tag**
   - Click on your account name (top right)
   - Select "Account Assets" → "Insight Tag"
   - Click "Install my Insight Tag"
   - You'll see your Partner ID (6-digit number)

3. **Get your Partner ID**
   - It looks like: `123456` (6 digits)
   - Copy this number

4. **Update your HTML files**
   - Open each file: `index.html`, `desktop.html`, `mobile.html`
   - Find the line: `"YOUR-LINKEDIN-PARTNER-ID"`
   - Replace `YOUR-LINKEDIN-PARTNER-ID` with your actual Partner ID (in **TWO** places per file)

5. **Verify installation**
   - Go back to LinkedIn Campaign Manager → Insight Tag
   - Within 24 hours, you should see "Active" status

### What LinkedIn Insight Tag Provides:
- **Website Demographics**: See LinkedIn profile data of visitors (aggregated)
- **Conversion Tracking**: Track form fills, downloads, contact clicks
- **Retargeting Audiences**: Create audiences for LinkedIn ads
- **Analytics**: Understand which companies/industries visit your site

---

## 4. Verify Everything Works

After setting up all tools, test your implementation:

### Test Checklist:

- [ ] **Visit your website** - You should see Cookiebot consent banner
- [ ] **Accept cookies** - Banner should disappear
- [ ] **Open browser console** (F12) - No JavaScript errors
- [ ] **Check GA4**: Go to https://analytics.google.com/ → Realtime → Should see your visit
- [ ] **Check Clarity**: Go to https://clarity.microsoft.com/ → Your project → Should see "Setup successful"
- [ ] **Check LinkedIn**: Go to Campaign Manager → Insight Tag → Should see "Verifying" (will turn "Active" in 24h)
- [ ] **Test cookie rejection**: Clear cookies, revisit site, click "Reject" → No tracking should fire

### Browser Console Check:
1. Visit your site
2. Press F12 to open Developer Tools
3. Go to "Console" tab
4. Look for:
   - `Cookiebot initialized` (or similar)
   - No red error messages
   - If you see errors about "YOUR-COOKIEBOT-ID-HERE", you haven't updated the IDs yet

---

## 5. Quick Reference - Where to Find Your IDs

| Tool | Where to Find ID | What It Looks Like | Location in Code |
|------|-----------------|-------------------|------------------|
| **Cookiebot** | Cookiebot Dashboard → Domain Settings | `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx` | `data-cbid="..."` |
| **Clarity** | Clarity Dashboard → Setup → Project ID | `abcd1234ef` | `"clarity", "script", "..."` |
| **LinkedIn** | Campaign Manager → Insight Tag | `123456` (6 digits) | `_linkedin_partner_id = "..."` |

---

## 6. Privacy & Compliance

Your implementation is now privacy-compliant:

✅ **GDPR Compliant**: Cookiebot handles consent management
✅ **CCPA Compliant**: Users can opt-out via consent banner
✅ **IP Anonymization**: GA4 configured with `anonymize_ip: true`
✅ **Consent-Gated**: All tracking scripts only load after user consent

### Data Processing:
- **GA4**: Statistics cookie (requires consent)
- **Clarity**: Statistics cookie (requires consent)
- **LinkedIn**: Marketing cookie (requires consent)

---

## 7. Monitoring & Analytics Access

After setup, access your analytics here:

| Tool | Dashboard URL | What You'll See |
|------|--------------|----------------|
| **GA4** | https://analytics.google.com/ | Traffic, conversions, user behavior |
| **Clarity** | https://clarity.microsoft.com/ | Heatmaps, recordings, insights |
| **LinkedIn** | https://www.linkedin.com/campaignmanager | Demographics, conversions |
| **Cookiebot** | https://manage.cookiebot.com/ | Consent statistics, compliance reports |

---

## 8. Estimated Time Investment

| Task | Time Required | Difficulty |
|------|--------------|------------|
| Cookiebot Setup | 10 minutes | Easy |
| Clarity Setup | 5 minutes | Very Easy |
| LinkedIn Setup | 10 minutes | Easy |
| Testing | 5 minutes | Easy |
| **TOTAL** | **30 minutes** | **Easy** |

---

## 9. Troubleshooting

### Cookiebot banner not showing?
- Check that you replaced `YOUR-COOKIEBOT-ID-HERE` with actual ID
- Open browser console (F12) - look for errors
- Try clearing cache (Ctrl+Shift+R)

### Clarity not recording?
- Make sure you replaced `YOUR-CLARITY-ID-HERE` with actual ID
- Check Clarity dashboard "Setup" status
- It can take 5-10 minutes for first data to appear

### LinkedIn tag not active?
- Make sure you replaced BOTH instances of `YOUR-LINKEDIN-PARTNER-ID`
- LinkedIn verification takes up to 24 hours
- Check Campaign Manager → Insight Tag for status

### GA4 not tracking?
- Cookiebot must be configured first (users need to consent)
- Check GA4 Realtime view (data appears within seconds)
- Make sure ad blockers are disabled for testing

---

## 10. Next Steps

After completing setup:

1. **Monitor for 1 week** - Check all dashboards to ensure data is flowing
2. **Set up GA4 goals** - Track form submissions, email clicks, LinkedIn clicks
3. **Create Clarity insights** - Set up custom tags for important page elements
4. **LinkedIn conversion tracking** - Set up specific conversion events if running ads
5. **Regular review** - Check Cookiebot consent rates, optimize banner if needed

---

## Support Resources

- **Cookiebot Support**: https://support.cookiebot.com/
- **Clarity Help**: https://learn.microsoft.com/en-us/clarity/
- **LinkedIn Insight Tag**: https://business.linkedin.com/marketing-solutions/insight-tag
- **GA4 Documentation**: https://support.google.com/analytics/

---

**Last Updated**: 2025-11-29
**Maintained By**: Matt Schober

---

## Appendix: Files Modified

The following files have been updated with tracking code:
- `index.html` - Redirect page (includes all tracking)
- `desktop.html` - Desktop version (includes all tracking)
- `mobile.html` - Mobile version (includes all tracking)

All tracking scripts include `data-cookieconsent` attributes to ensure they only load with user consent.
