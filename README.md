# Pickleball Party

A sign-up and game-day site for a beginner-friendly pickleball social, hosted on GitHub Pages with Google sign-in.

**Format: rotating partners.** Everyone gets a new partner every game. Wins and points go on a live leaderboard, and the top 4 finish with a championship game (#1 & #4 vs #2 & #3).

- **Players** sign in with Google and register (their name, an optional spouse or friend, and how many kids are coming). On their phone they get a bottom bar with **Event**, **My games** (their court, partner and results), **Now playing**, **Leaderboard** and **Rules**.
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
2. In **Setup**, fill in the date, time, location and the notes for players (cost, food, potluck, what to bring). Leave **Registration open** on.
3. Copy the site link and send it to everyone. They tap **Sign in with Google to register**. The **Rules** page is open to everyone, so beginners can read it ahead of time.
4. Check **Players** as people sign up, including what each person is bringing. The Event page also shows everyone a "What people are bringing" list, which refreshes whenever you have the site open as admin. Add walk-ins there too. Put couples on one line with a plus sign (`Eddie + Jess`) so they aren't paired as partners.

## On the day

1. In **Players**, untick **Playing** for anyone who isn't there yet. Tick them back in when they arrive.
2. In **Setup**, turn on **Show courts, partners and leaderboard to everyone**.
3. On **Play**, tap **Start round 1**. Everyone's phone shows their court and partner.
   - Need a change before a game starts? Tap two names to swap them, or tap **Reshuffle**.
4. Enter each score as games finish. When all are in, tap **Start round 2**, and so on.
5. After the last round (7 by default), tap **Start championship game**. The top 4 play #1 & #4 vs #2 & #3 on Court 1, and everyone else plays one more game.
6. The Leaderboard shows the champions and runners-up with their prizes.

## How the rounds are built

- Nobody gets the same partner twice until it can't be avoided, and repeat opponents are kept low.
- Games are balanced using each player's win rate so far.
- With uneven numbers, the extra players **sit out in turns**: never twice in a row, and everyone sits about the same number of times. With **Players sitting out watch the kids' zone** on (in Setup), they're shown as watching the kids.
- 16 players fills 4 courts, 12 fills 3. With 13–15, 1–3 people sit out each round.
- The leaderboard ranks by win rate, then point difference, so sitting out never hurts anyone.

## Good to know

- Players can edit or cancel their own registration while registration is open.
- **Setup → Backup** exports everything as a file anytime. **Clear all rounds** wipes the games but keeps players and settings, which is handy after a practice run.
