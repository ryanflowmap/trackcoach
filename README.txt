# TrackCoach — Setup Instructions

## Files in this package
- index.html       — Main app
- manifest.json    — PWA install config
- sw.js            — Offline service worker
- firestore.rules  — Database security rules
- icons/           — App icons

---

## Step 1: Upload to GitHub Pages (same as before)
1. Go to your existing trackcoach repo on GitHub
2. Delete all old files (or just replace them)
3. Upload ALL files from this zip (including the icons folder)
4. Commit — your site updates automatically at https://YOUR-USERNAME.github.io/trackcoach

---

## Step 2: Update Firestore Security Rules
1. Go to Firebase Console → Firestore Database → Rules tab
2. Replace everything with the contents of firestore.rules
3. Click Publish

---

## Step 3: Set up your own account (IMPORTANT — do this first)
Because you are the admin, you need to create your account BEFORE
the approval system locks things down:

1. Open your app URL in Safari
2. Tap "Request Access"
3. Enter your name, ryan.flowmap@gmail.com, and a password
4. Go to Firebase Console → Firestore → users collection
5. Find your document and change status from "pending" to "approved"
6. Sign in — you now have full access

---

## Step 4: Approving new coaches
When someone requests access:
1. You'll see a new document in Firebase → Firestore → notifications collection
2. Go to Firebase → Firestore → users collection
3. Find their document (by email)
4. Change their status field from "pending" to "approved"
5. They can now sign in

To get email alerts when someone requests access:
1. In Firebase Console → go to Extensions
2. Install "Trigger Email" extension
3. Connect it to SendGrid or your Gmail SMTP
4. It will watch the notifications collection and email ryan.flowmap@gmail.com automatically

---

## Step 5: Install on iPhone (same as before)
1. Open your GitHub Pages URL in Safari
2. Tap Share → Add to Home Screen
3. Done

---

## What's new in this version
- Login / access request system with pending approval
- New meet defaults to all track + field events pre-loaded
- Track events separated from field events (boys/girls)
- Middle school grades (6th, 7th, 8th) added
- Results rankings use dropdown event filter instead of pills
- Runner profiles show as a list — tap a runner to see their results
- Export to CSV (Excel) or PDF
- Stopwatch event selector groups track vs field events
