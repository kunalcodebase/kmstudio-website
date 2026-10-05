# KMStudio — Netlify + Decap CMS Setup Guide

Your website is now prepared for **Decap CMS** (formerly Netlify CMS).

---

## What You Have Now

```
KMStudio/
├── index.html              ← Your public website
├── admin/
│   ├── index.html          ← CMS login & dashboard
│   └── config.yml          ← CMS configuration
├── data/
│   ├── settings.json       ← Editable site settings
│   ├── hero.json           ← Hero section content
│   ├── about.json          ← About section
│   ├── services/           ← Individual service cards
│   └── process/            ← Process steps
├── images/uploads/         ← Media uploads folder
└── netlify.toml            ← Netlify configuration
```

---

## Step-by-Step Setup (Required)

### 1. Create a GitHub Repository
1. Go to [github.com](https://github.com) and create a new repository (e.g. `kmstudio-website`)
2. Upload **all** the files from this folder to the repository
3. Make sure the default branch is `main`

### 2. Deploy on Netlify
1. Go to [netlify.com](https://www.netlify.com) → Sign up / Log in
2. Click **Add new site** → **Import an existing project**
3. Connect your GitHub account and select the repository
4. Build settings:
   - **Build command**: leave empty
   - **Publish directory**: `.` (or leave default)
5. Click **Deploy site**

### 3. Enable Netlify Identity (for login)
1. In your Netlify site dashboard → **Site configuration** → **Identity**
2. Click **Enable Identity**
3. Under **Registration preferences** → set to **Invite only** (recommended)
4. Go to **Services** → **Git Gateway** → **Enable Git Gateway**

### 4. Invite Yourself as Admin
1. Still in Identity → **Invite users**
2. Enter your email → Send invite
3. Check your email and accept the invitation
4. Set a password

### 5. Access the CMS
After deployment, open:

**https://your-site-name.netlify.app/admin/**

or once you connect the domain:

**https://kmstudio.tech/admin/**

Log in with the email you invited.

---

## What You Can Edit from the CMS

| Collection        | What you can change                          |
|-------------------|----------------------------------------------|
| Site Settings     | Title, tagline, email, phone                 |
| Hero Section      | Headline, subtext, buttons                   |
| Services          | Add / edit / reorder service cards           |
| About Section     | Text and feature points                      |
| Process Steps     | The 4-step process                           |
| Homepage (Full)   | Advanced – edit the entire HTML if needed    |

---

## Important Notes

- The current `index.html` is still a **static** file. The data files (`data/*.json`) are ready for the CMS, but the HTML does not yet dynamically load them.
- For a fully dynamic experience (where changing JSON instantly updates the live site), we would need a static site generator (11ty, Hugo, Astro, etc.).
- Right now you can:
  1. Use the CMS to manage content in the `data/` folder
  2. Or use the “Homepage (Full HTML)” collection to edit the whole page

---

## Connecting Your Domain (KMStudio.tech)

1. In Netlify → **Domain management** → **Add custom domain**
2. Enter `kmstudio.tech`
3. Follow the DNS instructions (usually add a CNAME or A record at your domain registrar)

---

## Form Submissions (Leads)

You still have two good options:

**Option A – Formspree** (already prepared in the form)  
Just replace `YOUR_FORM_ID` in `index.html`

**Option B – Netlify Forms**  
Add `netlify` attribute to the `<form>` tag and submissions appear in your Netlify dashboard under Forms.

---

Need help with any step? Just ask!
