Tablet Tracker — Realtime Today-Only
==================================
Upload these files to any static host (Cloudflare Pages Upload, Replit Static HTML, Netlify, Vercel).
On first run, paste your Firebase Web App config and an Org ID. That’s it.

What it does:
- Hardcoded tablets 51–99
- Status: unused / purchased / maintenance (maintenance excluded from totals and sorted to bottom)
- Big counters (Purchased / Not Purchased / Maintenance)
- Filter + search, customer field
- Realtime sync via Firestore
- Today-only (resets by PIN button)
- PIN for reset: 4321 (change in code if you want)

Firestore Rules (starter):
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /orgs/{orgId}/days/{day}/tablets/{tabletId} {
      allow read, write: if request.auth != null;
    }
  }
}
Enable Firestore and Anonymous Auth in Firebase.
