# Pickleball Party

A sign-up and game-day site for a beginner-friendly pickleball social, hosted on GitHub Pages with Google sign-in.

**Format: rotating partners.** Everyone gets a new partner every game. Points go on a live leaderboard, and the 3 players with the most total points win 1st, 2nd and 3rd.

- **Players** sign in with Google and register (their name, an optional spouse or friend, their experience level, whether they need to borrow a paddle, and how many kids are coming). On their phone they get a bottom bar with **Event**, **My games** (their court, partner and results), **Now playing**, **Leaderboard** and **Rules**.
- **You (admin)** get pages no one else can see: registrations with emails, walk-ins, who's playing, building each round, score entry, and settings.

Security comes from Firebase rules, not from hiding pages: only your Gmail can change the event or read registrations.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole site |
| `firebase-config.js` | Settings for the `pickleball-party-dd624` Firebase project (already filled in) |

## Firebase (done)

Project `pickleball-party-dd624` is set up: Google sign-in is on, `finalydev.github.io` is an authorized domain, the Firestore database exists, and the security rules are published with your Gmail as the only admin. To change the admin email later: Firebase console → Firestore Database → Rules, edit the email in `isAdmin()`, and Publish.

## Before the day

1. Open the site and **sign in with your admin Gmail**. You'll see the Admin badge and the organizer tabs.
2. In **Setup**, add a **Shared photo album link** (a Google Photos or iCloud shared album) if you want one. It shows as a Photos button on the Event page and Leaderboard. Fill in the date (the Event page then shows a countdown), time, location, address and parking directions (used for the Google and Apple Maps buttons), and the notes for players (for example, "Pizza provided"). Leave **Registration open** on.
3. Copy the site link and send it to everyone. They tap **Sign in with Google to register**. The **Rules** page is open to everyone, so beginners can read it ahead of time.
4. Check **Players** as people sign up. The **Paddles to bring** count tells you how many loaners to pack, and each player's level (New, Some, Regular) can be changed there. Add walk-ins there too. Everyone sees a **Who's coming** list on the Event page with names only (no emails). New sign-ups show up there while you have the site open, so open it now and then. Put couples on one line with a plus sign (`Eddie + Jess`) so they aren't paired as partners.

## On the day

1. In **Players**, untick **Playing** for anyone who isn't there yet. Tick them back in when they arrive.
2. In **Setup**, turn on **Show courts, partners and leaderboard to everyone**.
3. On **Play**, tap **Start round 1**. Everyone's phone shows their court and partner.
   - Need a change before a game starts? Tap two names to swap them, or tap **Reshuffle**.
4. Enter each score as games finish, or let players do it: they send their score from **My games**, the **Play** tab shows a red badge, and you tap **Approve** (or **Dismiss**). Turn this off in Setup if you'd rather enter every score yourself. When all are in, tap **Start round 2**, and so on.
5. After the last round (7 by default), tap **Finish and announce top 3**. You can also finish early after any round, or tap **Play another round** if there's time.
6. The Leaderboard shows the top 3 with their prizes (set them in **Setup → Prizes**). Tap **Undo finish** on Play if you need to keep going.

## How the rounds are built

- Nobody gets the same partner twice until it can't be avoided, and repeat opponents are kept low.
- Games are balanced using each player's win rate so far. Before anyone has played, the experience level they picked at sign-up does the balancing, and it matters less as results come in.
- **Kids' zone watchers:** with **Players sitting out watch the kids' zone** on, set **At least this many sit out each round** (2 by default) in Setup → Format. The site leaves enough people off the courts every round, even with exactly 12 or 16 players, and Format shows how many games each person gets. For only 2 courts at a time, set **Courts** to 2.
- With uneven numbers, the extra players **sit out in turns**: never twice in a row, and everyone sits about the same number of times. With **Players sitting out watch the kids' zone** on (in Setup), they're shown as watching the kids.
- 16 players fills 4 courts, 12 fills 3. With 13–15, 1–3 people sit out each round.
- The leaderboard ranks by total points scored, then wins, then point difference. With 13–15 players, some people sit out one more round than others, which costs them a game's worth of points.

## Event chat

- Everyone signed in can read the **Chat** tab; registered players and you can post. Your messages show a **Host** tag.
- A red badge on the Chat tab shows unread messages.
- People can delete their own messages, and you can delete any message.
- **Clear chat** (on the Chat tab) or **Reset everything** (in Setup) starts a fresh, empty chat. Turn it off anytime with **Event chat on** in Setup.

## Good to know

- Players can edit or cancel their own registration anytime, even after you close registration.
- On **Players**, tap **Edit** under anyone's name to change their name, their spouse or friend's name, their food item or note. Players who share a name get a red **Same name** tag so you know to rename one (for example, "Sam L."). For walk-ins, tap ✎ on their row to change their name, who they came with, their food, or a private note.
- Anyone can add what food or drinks they're bringing. Everyone sees a **Who's bringing what** list on the Event page and under the sign-up box, so dishes don't double up.
- **Setup → Backup** exports everything as a file anytime. **Clear all rounds** wipes the games but keeps players and settings, which is handy after a practice run.
