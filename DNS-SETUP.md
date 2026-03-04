# journeyadhd.org → DNS Setup Instructions

## Option A: GitHub Pages (current staging)

### Step 1: Add custom domain in GitHub
Already configured. The site is live at:
https://andrewsteinmeyer.github.io/journey-adhd-website/

### Step 2: DNS Records (at your domain registrar)
Add these DNS records for `journeyadhd.org`:

**For apex domain (journeyadhd.org):**
```
Type: A
Name: @
Value: 185.199.108.153

Type: A
Name: @
Value: 185.199.109.153

Type: A
Name: @
Value: 185.199.110.153

Type: A
Name: @
Value: 185.199.111.153
```

**For www subdomain:**
```
Type: CNAME
Name: www
Value: andrewsteinmeyer.github.io
```

### Step 3: Enable custom domain in GitHub repo
Go to: https://github.com/andrewsteinmeyer/journey-adhd-website/settings/pages
- Enter `journeyadhd.org` in the Custom Domain field
- Check "Enforce HTTPS"

---

## Option B: Webflow (if migrating later)

### Step 1: Add site to Webflow
Create new project in Webflow, build/import the site.

### Step 2: DNS Records for Webflow
```
Type: A
Name: @
Value: 75.2.70.75

Type: CNAME
Name: www
Value: proxy-ssl.webflow.com
```

### Step 3: Add custom domain in Webflow
Project Settings → Hosting → Add Custom Domain → `journeyadhd.org`

---

## Notes
- DNS propagation takes 15 min to 48 hours (usually under 1 hour)
- HTTPS certificate auto-provisions on both platforms
- The GitHub Pages site is ready for production right now
