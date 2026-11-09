# Pickleball Party Tournament

A tournament site for GitHub Pages with Google sign-in.

- **Players** sign in with Google and register: their name, an optional spouse or partner (always put on a different team), and how many kids are coming. They can see their registration, whether they've paid, their team, and their games highlighted on the schedule.
- **You (admin)** get the organizer pages that no one else can see: registrations with emails, payments, walk-ins, the team draw, pools, schedule, score entry, brackets and the raffle (one ticket per player).
- **Players** use a phone-friendly bottom bar: **Event** (details and sign-up), **My games** (their team, next game and results), **Now playing**, **Schedule** and **Results**. Those pages appear once you turn on "Show teams, schedule and results". Scores update live on every phone.

Security comes from Firebase rules, not from hiding pages: only your Gmail can change the tournament or read registrations.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole site |
| `firebase-config.js` | Settings for the `pickleball-party-dd624` Firebase project (already filled in) |
| `firestore.rules` | Copy of the security rules already published in Firebase. Keep it for reference; don't upload it, since it contains your email |

## 1. Firebase (done)

Project `pickleball-party-dd624` is set up:

- Google sign-in is turned on, with "Pickleball Party" as the name players see when they sign in.
- `finalydev.github.io` is an authorized domain, so sign-in works on your GitHub Pages site.
- The Firestore database is created and the security rules are published, with your Gmail as the only admin.
- The web app is registered and its settings are in `firebase-config.js`.

To change the admin email later: Firebase console → Firestore Database → Rules, edit the email in `isAdmin()`, and Publish.

The values in `firebase-config.js` are meant to be public. Security comes from the rules.

## 2. Put it on GitHub Pages

1. Create a new repo, for example `pickleball-party`.
2. Upload `index.html`, `firebase-config.js` and this README.
3. Settings → **Pages** → Source: *Deploy from a branch* → `main` / `(root)` → Save.
4. In a minute the site is live at `https://finalydev.github.io/pickleball-party/`.

## 3. First run

1. Open the site and **sign in with your admin Gmail**. You'll see the Admin badge and the organizer tabs. This first sign-in also creates the tournament record, so do it before sharing the link.
2. In **Setup**, fill in the date, time, location, cost and the notes for players (food, potluck or what's included). Leave **Registration open** on.
3. Copy the site link and send it to everyone. They tap **Sign in with Google to register**.
4. Check **Players** as people sign up: emails, kids count, paid checkboxes, money collected and total guest count. Add walk-ins there too.
5. On the day: close registration, **Teams & Pools** → Draw teams → Draw pools → Reveal teams one by one → Generate schedule. Then turn on **Show teams, schedule and results** in Setup.
6. Run rounds from **Now playing**: enter scores as games finish, and seed the brackets after pool play.

## Good to know

- Before Firebase is set up, the site runs in **local mode**: no sign-in, everything on one device. Handy for a practice run.
- Players can edit or cancel their own registration while registration is open. Only you can mark someone paid.
- Removing a registration on the Players page removes those players from the draw. Redraw teams if that happens after the draw.
- **Setup → Backup** exports the tournament as a file anytime.
