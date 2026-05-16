# cnattitle.tech

Tactical static site for CNAT Title — post-closing review hub and a redirect-only apex.

## What's here

| Path | Purpose |
|------|---------|
| `/review` | Landing page after closing — picks "Great experience" vs "I have feedback" |
| `/locations-picker` | Picks which CNAT office for the Google review (6 locations) |
| `/feedback-form` | Private feedback form — posts to n8n → GHL CNAT |
| `/thank-you` | Confirmation after feedback submit |
| `/` (apex) | 301 → cnattitle.com |
| (any other path) | 301 → cnattitle.com |

## Migrated from GoHighLevel

This used to be a GHL Funnel attached to `cnattitle.tech` (apex). Migrated to static HTML for editability and speed. The form data still lands in the CNAT GHL sub-account via webhook.

## Form backend

`feedback-form` posts JSON to:

```
https://n8n.cnattitle.tech/webhook/cnat-web-review-feedback
```

That n8n workflow ("CNAT cnattitle.tech — Review Feedback → GHL", id `jV8NSQOhdHXovMks`):
1. Upserts a contact in GHL CNAT (`9ZNjcEKhpBno9RRXrBA4`)
2. Adds a private-feedback note with the full message
3. Tags `src:webform`, `form:review-feedback`, `feedback:private`, `priority:high`
4. Emails `marketing@cnattitle.com`
5. Returns `{success: true, contactId}`

## Deploy

Hosted on Hostinger with native git auto-deploy.
- Repo: `iambradass/cnattitle-tech` (public)
- Push to `main` → live in ~30-60s
- After deploy: flush CDN in hPanel → Hosting → Cache Manager → Flush All

## QR code

`/assets/qr-review.png` — branded QR for `https://cnattitle.tech/review`. Drop into closing packets, email signatures, table tents, flyers.
