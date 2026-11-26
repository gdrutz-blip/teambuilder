# Gym Team Maker

Balanced gym teams in seconds, made for a phone or a projector. **Everything is in one file, `index.html`**. It makes no network requests (a Content-Security-Policy blocks them), and student data is stored only in your browser's localStorage.

## Getting started
1. Download `index.html` and double-click it (Chrome, Edge or Firefox), or use the GitHub Pages link (see below).
2. **Data → Load sample data** to try it with 58 fake students.
3. For real use:
   - Build the Google Form from [FORM.md](FORM.md).
   - Paste each class list in **Students & rules → Class list**.
   - Import the responses CSV in **Data**.

## Each class
1. Pick **class**, **sport** and **number of teams** (2–6).
2. Tap absent or injured students (they turn grey).
3. **Make teams**.

## After the teams are made
- **Swap:** tap a name, then tap a name on another team. **Move:** tap a name, then **Move here** on another team. On a computer you can also drag.
- **Lock** a student (or a whole team) so they stay put; **Shuffle** then rebalances everyone else.
- **Late arrival:** tap their name in *Who's playing* (or **＋ Add student**). They're placed on the best-fitting team.
- **Someone leaves:** tap their name, then **Left / absent**.
- Toggle **Strength**, **Boys/Girls**, **Friend report** and **Schedule** before projecting, or use **Projector view**.
- **Copy as text** and **Print** (one page; includes the 2-court round-robin for 3, 4 or 5 teams).
- 8A and 8B keep their own teams and attendance, so you can switch back and forth.

## Split by level (competitive / casual)
Turn on **Split by level** on the Teams tab, then pick how many teams go to **Competitive** and how many to **Casual** (e.g. 2 + 4).
- Each student's answer for the chosen sport decides their group. **Either** (or no answer) fills whichever group is short, strongest Either players to Competitive first.
- The **Level groups** card previews the split. **Tap a name to move them** to the other group before pressing Make teams. Moves are saved per class and sport; "Undo moves" clears them.
- Each group is balanced separately with the same rules. Level comes before friends, so a friend in the other group is noted in the friend report.
- Round-robin schedules are per group (groups of 3–6 teams).
- If a group doesn't have enough players, the tool says so rather than choosing for you. Change the team counts or move students.

## Even boys/girls toggle
**Even boys/girls** (Teams tab) switches the boy/girl balancing on or off. When on, each team gets at least 2 boys and 2 girls when numbers allow, lowered automatically when fewer are present. When off, gender is ignored.

## Help tab, classes and sharing
The **Help** tab inside the tool explains how to build the form and use the tool, so colleagues can use the Pages link without seeing the repo. Classes come from the form's Class answers and can be added, renamed or removed under **Data → Classes**. **Data → Download sample CSV** shows the expected format. To show a "make a copy" button for a template form, paste its link into `FORM_TEMPLATE_URL` near the top of `index.html`.

## Short friend lists
A student who lists only 1 or 2 friends has their request honoured on about 60% / 85% of shuffles (instead of every time), so they aren't paired with the same person every day. Lists of 3 or more always count in full. The change is the `LIGHT_P` setting in `index.html`.

## How teams are balanced (in priority order)
1. Team sizes as even as possible (hard rule).
2. Teacher "always together" / "keep apart" rules.
3. At least 2 boys and 2 girls per team when the numbers allow, then boys and girls spread evenly.
4. Strength totals for the chosen sport as close as possible. A 1–2 point give is allowed if it gets more kids a friend.
5. Everyone gets at least one requested friend where possible.
6. Students' "not with" requests.
7. Top players spread across teams.

The optimizer does 24 random starts with simulated annealing plus swap hill-climbing (about 50 ms). Shuffle picks a different near-best result each time.

## Teacher overrides (Students & rules)
- Set gender (B/G/–) for students who skipped it.
- Adjust a student's strength per sport with − / +. Blue means overridden; **reset** goes back to their rating.
- Always-together / keep-apart pairs.
- Add or delete students; paste class lists.

## Backup / privacy
- Data lives in the browser you use. Use **Data → Download backup** to move it to another device.
- **Clear all data** wipes everything.
- On GitHub Pages the page is public, but it only contains the fake sample names. Your real data still stays on your own device.

## Publishing with GitHub Pages (optional)
Repo **Settings → Pages → Build and deployment → Deploy from a branch** → pick the branch with `index.html` and `/ (root)` → Save. Free accounts need the repo to be public for Pages.
