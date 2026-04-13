# CURIOSUM | Infrastructure & Email Administration Summary

**Prepared:** April 2026 | **Status:** Email Live, Website Pending

---

## 1. Domains Overview

| Domain | Registrar | Expires | Status |
|---|---|---|---|
| **curiosum.ai** | Crazy Domains | TBC | ✅ Active — PRIMARY |
| **curiosum.co.nz** | Crazy Domains | 31 Mar 2028 | ✅ Active — Secondary |

---

## 2. Email Platform

| | |
|---|---|
| **Provider** | Zoho Workplace Standard |
| **Plan** | Standard — NZ$5/user/month (billed annually) |
| **Current Billing** | ⚠️ Monthly — switch to Annual to save ~17% |
| **Users** | 6 accounts on curiosum.ai |
| **Storage** | 30GB per user + 100GB shared WorkDrive |
| **Admin Portal** | mailadmin.zoho.com.au |
| **Webmail** | mail.zoho.com.au |

---

## 3. Email Accounts

| Email Address | User | Role | Status |
|---|---|---|---|
| hamish@curiosum.ai | Hamish Carr | Founder & CEO | ✅ Active |
| scott@curiosum.ai | Scott | Team | ✅ Active |
| hello@curiosum.ai | Shared Inbox | General Contact | ✅ Active |
| ab@curiosum.ai | Ab | Team | ✅ Active |
| vatsalya@curiosum.ai | Vatsalya | Team | ✅ Active |
| jalaaaj@curiosum.ai | Jalaaaj | Team | ✅ Active |

*Note: hello@curiosum.ai is a shared general inbox managed by Hamish Carr.*

---

## 4. DNS Configuration — curiosum.ai

All records verified and active in Crazy Domains DNS Settings.

| Type | Host | Value | Priority | Status |
|---|---|---|---|---|
| TXT | @ | zoho-verification=zb33563732.zmverify.zoho.com.au | - | ✅ Active |
| MX | @ | mx.zoho.com.au | 10 | ✅ Active |
| MX | @ | mx2.zoho.com.au | 20 | ✅ Active |
| MX | @ | mx3.zoho.com.au | 50 | ✅ Active |
| TXT (SPF) | @ | v=spf1 include:zohomail.com.au ~all | - | ✅ Active |
| TXT (DKIM) | zmail._domainkey | v=DKIM1; k=rsa; p=[key] | - | ✅ Active |

---

## 5. Email Client Configuration

Share these settings with team members when setting up Outlook, Apple Mail or mobile apps.

| Setting | Value | Port | SSL |
|---|---|---|---|
| Incoming (IMAP) | imap.zoho.com.au | 993 | Yes |
| Incoming (POP) | pop.zoho.com.au | 995 | Yes |
| Outgoing (SMTP) | smtp.zoho.com.au | 465 / 587 | Yes |

- Username = full email address e.g. hamish@curiosum.ai
- Webmail access: mail.zoho.com.au (no setup required)
- Mobile app: Search 'Zoho Mail' in App Store or Google Play

---

## 6. Recommended Email Signature

> **Hamish Carr**
> Founder, Curiosum
>
> *Be Curious. Think Differently. Transform Deliberately.*
>
> curiosum.ai

*To add signature in Zoho: Mail > Settings (gear icon) > Signatures > New Signature*

---

## 7. Website Hosting — Action Required

> ⚠️ **Website is NOT yet published. curiosum.ai currently points to Crazy Domains placeholder.**

### Recommended: Netlify (Free)

1. Sign up at netlify.com
2. Deploy website: drag and drop your HTML folder into Netlify
3. Add custom domain: Site Settings > Domain Management > Add curiosum.ai
4. Update DNS in Crazy Domains: change A records to Netlify's IP (provided by Netlify)
5. SSL certificate: automatic, free via Let's Encrypt

*Note: The two existing A Records in Crazy Domains (pointing to 27.124.125.171) will need to be updated to Netlify's addresses once the site is deployed.*

---

## 8. Outstanding Items

| Task | Details | Priority |
|---|---|---|
| Switch Zoho to Annual Billing | Currently on monthly. Switch to annual (NZ$5/user/month) to save ~17%. Zoho Admin > Subscription. | **HIGH** |
| Add Email Signature | Add to hamish@curiosum.ai: Hamish Carr, Founder Curiosum, Be Curious. Think Differently. Transform Deliberately. curiosum.ai | **HIGH** |
| Publish Website to Netlify | Sign up at netlify.com, deploy HTML files, connect curiosum.ai domain. Update A records in Crazy Domains DNS. | **HIGH** |
| Call Each Team Member | Give each user their login credentials by phone. Direct them to mail.zoho.com.au. | **HIGH** |
| Force Password Change on First Login | Confirm each user (except hello@) changes password on first login. | **MEDIUM** |
| Add curiosum.co.nz as Domain Alias | Add curiosum.co.nz as secondary domain in Zoho so @curiosum.co.nz emails also work. | **MEDIUM** |
| Delete Old cPanel Email Accounts | Remove the 5 curiosum accounts created in Crazy Domains cPanel. Login to cPanel > Email Accounts > delete ab@, hello@, jalaaaj@, scott@, vatsalya@ from cPanel. | **MEDIUM** |
| Set Up Zoho WorkDrive | Create team folders for file sharing. All 6 users have access via Workplace Standard. | **LOW** |
| Set Up Zoho Cliq | Team chat is included. Set up channels for the team when ready. | **LOW** |
| Plan Supabase Integration | When ready for customer logins + file storage, set up Supabase as backend. Works alongside Netlify. | **FUTURE** |

---

## 9. Technology Stack Summary

| Layer | Tool | Purpose | Status |
|---|---|---|---|
| Domain | Crazy Domains | Domain registration & DNS | ✅ Live |
| Email | Zoho Workplace Standard | Team email & collaboration | ✅ Live |
| Website Hosting | Netlify (free) | Static site hosting + SSL | ⏳ Pending |
| Backend (future) | Supabase (free tier) | Auth, database, file storage | 🔮 Planned |
| Document AI (future) | Anthropic Claude API | Document processing & AI | 🔮 Planned |

---

*Be Curious. Think Differently. Transform Deliberately.*

*Confidential — Curiosum Internal Document | curiosum.ai | April 2026*
