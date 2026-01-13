# GitHub Pages Pricing Setup Guide

## Files Generated

1. **README_PRICING_SECTION.md** - Copy/paste this section into your main README.md
2. **docs/pricing.html** - Interactive Stripe checkout page deployed via GitHub Pages

---

## Deployment Steps

### Step 1: Add README Section

Add the content from `README_PRICING_SECTION.md` to your main README.md.

**Recommended Location**: After the notebook descriptions, before the "Contributing" section.

### Step 2: Enable GitHub Pages

The pricing.html file has been placed in the `docs/` folder. Now enable GitHub Pages:

1. Go to your KASS repo: https://github.com/bcdelodx/KASS
2. Click **Settings** (top menu)
3. Click **Pages** (left sidebar)
4. Under "Build and deployment":
   - **Source**: Select "Deploy from a branch"
   - **Branch**: Select "main" (or your default branch)
   - **Folder**: Select "/docs"
5. Click **Save**

### Step 3: Commit and Push

```bash
cd /Users/bcdelo/Documents/GitHub/KRL/KASS

# Stage the new files
git add docs/pricing.html
git add README_PRICING_SECTION.md
git add GITHUB_PAGES_SETUP_GUIDE.md

# Commit (without Claude co-authorship)
git commit -m "Add interactive pricing page with Stripe integration"

# Push to GitHub
git push origin main
```

### Step 4: Verify Deployment

1. Wait 2-5 minutes for GitHub Pages to build
2. Visit: https://bcdelodx.github.io/KASS/pricing.html
3. Confirm Stripe pricing table loads correctly
4. Test checkout flow (you can cancel before completing payment)

---

## File Structure

```
KASS/
├── README.md (update with pricing section)
├── docs/
│   └── pricing.html (GitHub Pages deployment)
├── README_PRICING_SECTION.md (reference for README)
├── GITHUB_PAGES_SETUP_GUIDE.md (this file)
├── notebooks/
│   ├── causal-inference/
│   └── applied-econometrics/
└── [other repo files]
```

---

## Stripe Configuration

### Current Settings

**Pricing Table ID:** `prctbl_1SpCKTLs3JtuSBvEv7hfAsxg`
**Publishable Key:** `pk_live_51SZmznLs3JtuSBvEav0ir0toFaZ3Ga7LNMkR9Kf16dgwqrBbr2rZA1RyCitgAYyo5ZmVl2olSGygWqGjCjZyLzOY001NMt69RF`

These are configured in `docs/pricing.html` on lines 262-264.

### Products Included in Pricing Table

All 15 live products with complete metadata:
- ✓ Community (Free tier)
- ✓ Professional ($299/month)
- ✓ Team ($899/month)
- ✓ Enterprise (Custom pricing)
- ✓ Time-pass rentals (1hr, 24hr, 7-day access)
- ✓ Inference bundles (10-pack, 50-pack crown models)
- ✓ Token packs (100, 500, 2500 TCU)
- ✓ Team seat add-ons
- ✓ Federated learning rounds
- ✓ Custom model deployments

---

## Customization Options

### Update Links

If you need to change any links in pricing.html:

**Lines to modify:**
- Line 277: Demo link (`https://krlabs.dev/demo`)
- Line 278: Documentation link (`https://docs.krlabs.dev`)
- Line 279: Sales email (`mailto:info@krlabs.dev`)
- Line 284: Repository link (`https://github.com/bcdelodx/KASS`)
- Line 288: Company website (`https://krlabs.dev`)
- Line 288: Contact email (`mailto:info@krlabs.dev`)

### Update Branding

**Header (lines 216-218):**
- Change title: "KRL Platform Pricing"
- Change subtitle to describe your offering

**Footer (lines 287-290):**
- Company name: "Khipu Research Labs"
- Copyright year: "2026"

### Update Value Props

The value proposition cards (lines 226-256) can be customized:
- Data connector count (currently 68+)
- Model count (currently 125+)
- Any other key differentiators

---

## Troubleshooting

### Pricing table doesn't load
- **Check GitHub Pages status**: Settings → Pages should show "Your site is live at..."
- **Verify HTTPS**: Stripe requires HTTPS (GitHub Pages provides this automatically)
- **Browser console**: Open DevTools (F12) and check for JavaScript errors
- **Stripe Dashboard**: Confirm pricing table ID is correct and published

### 404 Error on pricing page
- **Wait time**: GitHub Pages can take 5-10 minutes to deploy initially
- **Verify branch**: Ensure you pushed to the correct branch (main)
- **Check folder**: Confirm file is in docs/ folder, not root
- **Settings**: Double-check GitHub Pages is enabled and pointing to /docs

### Stripe checkout doesn't work
- **Live mode**: Verify you're using live publishable key (starts with `pk_live_`)
- **Test vs Live**: If using test key, ensure Stripe dashboard is in test mode
- **Product status**: Confirm all products in pricing table are active
- **Account status**: Verify Stripe account is fully activated (not restricted)

### Page loads but Stripe table is blank
- **Pricing table ID**: Verify ID matches what's in Stripe dashboard
- **Product configuration**: Ensure products have prices attached
- **Table settings**: Check Stripe pricing table settings are published

---

## Testing Checklist

Before announcing the pricing page:

- [ ] GitHub Pages deployed successfully
- [ ] Pricing page loads at https://bcdelodx.github.io/KASS/pricing.html
- [ ] Stripe pricing table displays all tiers
- [ ] All links work (demo, docs, repo, email)
- [ ] Mobile responsive (test on phone)
- [ ] Can initiate checkout flow
- [ ] Checkout redirects work (success/cancel URLs)
- [ ] README section added and renders correctly
- [ ] No Claude co-authorship in commit history

---

## Monitoring After Launch

### Track Metrics
- Page views: Use GitHub Pages analytics or Google Analytics
- Conversion rate: Stripe dashboard → Checkout sessions
- Popular tiers: Which products are being purchased?
- Drop-off points: Where do users abandon checkout?

### Iterate Based on Feedback
- A/B test CTA button text
- Try different pricing table layouts in Stripe
- Add customer testimonials once you have them
- Update feature lists as platform evolves

---

## Next Steps After Deployment

1. **Update Main README**: Copy content from README_PRICING_SECTION.md
2. **Test Everything**: Follow testing checklist above
3. **Announce**: Share pricing page in relevant channels
4. **Monitor**: Watch Stripe dashboard for first subscriptions
5. **Support**: Be ready to answer questions about pricing/features

---

## Support Resources

- **GitHub Pages Docs**: https://docs.github.com/pages
- **Stripe Pricing Tables**: https://stripe.com/docs/payments/checkout/pricing-table
- **KASS Repository**: https://github.com/bcdelodx/KASS
- **KRL Documentation**: https://docs.krlabs.dev

---

**Quick Deploy Commands:**

```bash
# Navigate to repo
cd /Users/bcdelo/Documents/GitHub/KRL/KASS

# Verify files are in place
ls -la docs/pricing.html
ls -la README_PRICING_SECTION.md

# Stage and commit
git add docs/pricing.html README_PRICING_SECTION.md GITHUB_PAGES_SETUP_GUIDE.md
git commit -m "Add interactive pricing page with Stripe integration"

# Push to GitHub
git push origin main

# Then enable GitHub Pages in repo settings
```

**After push, visit Settings → Pages and select:**
- Source: Deploy from a branch
- Branch: main
- Folder: /docs

Your pricing page will be live at: **https://bcdelodx.github.io/KASS/pricing.html**
