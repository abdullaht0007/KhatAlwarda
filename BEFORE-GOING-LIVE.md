# قبل الإطلاق — Before Going Live

---

## 🔴 One Thing Remaining — Cannot Launch Without This

### 1. Google Analytics ID ← DO THIS NOW
- Go to [analytics.google.com](https://analytics.google.com) and create a GA4 property
- Get your Measurement ID — it looks like `G-XXXXXXXXXX`
- Open `src/layouts/BaseLayout.astro`
- Find and replace **both** instances of `GA_MEASUREMENT_ID` with your real ID (line 64 and 69)
- Run `npm run build` after changing it

---

## 🟡 Your Side — Verify These Are Correct

### 2. Business Details
Confirm these are accurate (they appear in structured data and on every page):

| Detail | Current Value | Correct? |
|--------|--------------|----------|
| Phone | +966 55 295 9806 | ☐ Yes / ☐ No |
| WhatsApp | +966552959806 | ☐ Yes / ☐ No |
| Opening hours | Sat–Thu 8am–10pm | ☐ Yes / ☐ No |

### 3. Google Reviews Rating
- `src/pages/index.astro` shows `"ratingValue": "4.8"` and `"reviewCount": "47"` in structured data
- Update to match your **real** Google Maps rating once you have reviews
- Also update the `4.8` display number in the reviews section on the same file

### 4. "Write a Review" button
- Both review buttons currently link to your Google Maps pin
- Once you have a verified GBP review link (from Google Business Profile → "Ask for reviews"), replace the href in the reviews section of `src/pages/index.astro`

---

## 🟢 After Launch — Do These Once Live

### 5. Submit Sitemap to Google Search Console
1. Go to [search.google.com/search-console](https://search.google.com/search-console)
2. Add property → `https://khatalwarda.sa`
3. Verify ownership (download their HTML file → drop it in `public/`)
4. Go to **Sitemaps** → submit `https://khatalwarda.sa/sitemap-index.xml`

### 6. Set Up Google Ads
1. Create account at [ads.google.com](https://ads.google.com)
2. Link to your GA4 property
3. In GA4, mark `whatsapp_click` and `phone_call_click` as **Conversions**

### 7. Social Media Links
- Add Snapchat and Instagram links to the Footer (`src/components/Footer.astro`) once you have accounts

### 8. Real Customer Reviews
- After launch, ask customers for Google reviews via WhatsApp
- Once you reach 5+ reviews, update the rating numbers (item #3 above)

---

## ✅ Final Checklist Before Upload

- [ ] **GA4 Measurement ID replaced** in BaseLayout.astro (lines 64 + 69)
- [ ] Phone number confirmed correct
- [ ] WhatsApp number confirmed correct
- [ ] Opening hours confirmed correct
- [ ] Run `npm run build` — must say "Complete!" with no errors
- [ ] Upload `dist/` folder to hosting (Netlify / Cloudflare Pages)
- [ ] Visit the live URL and test WhatsApp button
- [ ] Visit the live URL and test phone number link
- [ ] Visit `/privacy` — privacy policy loads correctly
- [ ] Visit a broken URL (e.g. `/xyz`) — 404 page appears
- [ ] Share the link on WhatsApp — preview image appears
