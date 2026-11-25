# Google Form: Gym Team Survey

Build this in Google Forms. The tool reads the CSV export and works out the columns from their titles, so keep the key words shown in **bold** in each question title.

## Settings (gear icon)
- **Responses → Collect email addresses:** Off (or "Verified" if your school requires sign-in; the tool ignores the email column).
- **Limit to 1 response:** On, if students sign in with school accounts.
- **Allow response editing:** On. If a student submits twice anyway, the tool keeps the latest one.

Write every name as **First Last** (no commas), exactly the same as in your class lists.

---

## Section 1: Which class?
1. **Class** *(multiple choice, required)*: `8A`, `8B`
   - ⋮ menu → **Go to section based on answer**: 8A → Section 2, 8B → Section 3.

## Section 2: 8A *(after this section, go to Section 4)*
2. **Your name (8A)** *(dropdown, required)*: paste the 8A roster as options.
3. **Pick up to 6 friends you'd like on your team (8A)** *(checkboxes, optional)*: the 8A roster.
   - ⋮ → **Response validation** → "Select at most" → 6.

## Section 3: 8B *(after this section, go to Section 4)*
4. **Your name (8B)**: same as #2 with the 8B roster.
5. **Pick up to 6 friends you'd like on your team (8B)**: same as #3.

> Tip: build Section 2 completely, then use **Duplicate section** and swap the names and the "(8A)" labels.

## Section 4: About you
6. **Gender (optional)** *(multiple choice)*: `Boy`, `Girl`, `Prefer not to say`
7. **How good are you at each sport or game?** *(multiple-choice grid, "Require a response in each row" on)*
   - **Columns:** `1 - New to it`, `2`, `3 - Okay / not sure`, `4`, `5 - Very strong`
   - **Rows** (suggested list; delete any you never play). Don't leave a stray or misspelled row. A row named just `B`, for example, is ignored by the tool but clutters the form:
     - Basketball
     - Volleyball
     - Soccer
     - Floor Hockey
     - Badminton
     - Dodgeball
     - Ultimate Frisbee
     - Team Handball
     - Softball
     - Track & Field
     - Flag Football
     - Kickball
     - Pickleball
     - Lacrosse
     - Tchoukball
     - Capture the Flag
8. **Competitive or casual?** *(multiple-choice grid, "Require a response in each row" off)*
   - Title (any wording works as long as it contains "casual" or "competitive"), e.g. *"If there is an option, would you prefer to play a casual, more friendly game, or a more competitive game with more competitive rules?"*
   - **Columns:** `Competitive`, `Casual`, `Either`
   - **Rows:** the same sports as the skill grid in #7 (use the same names)
9. **Anything else your teacher should know? (optional)** *(paragraph)*: e.g. injuries, asthma, "I'm new to this sport".

Dropdowns also work for friends instead of checkboxes ("Friend 1" … "Friend 6", six dropdowns). The tool reads any column with "friend" in the title.

---

## Exporting
1. **Responses** tab → **Link to Sheets** (green icon).
2. In the Sheet: **File → Download → Comma-separated values (.csv)**.
3. In the tool: **Data → Choose CSV file…**

You can re-export and re-import any time, for example after late responses. Your overrides, locks and rules are kept.

## How the tool reads it
| In the CSV | How it's used |
|---|---|
| Ratings 1–5 | Strength for that sport |
| Competitive / Casual / Either per sport | Used by **Split by level**. Blank or no form = Either. |
| No rating / didn't do the form | Their average rating across sports, or 3 if none. Change it in **Students & rules**. |
| Misspelled names | Matched to your pasted class list. The import report shows each match. |
| Duplicate submissions | Latest timestamp wins |
