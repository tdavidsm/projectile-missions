# 🎯 Projectile Missions — Drop, Fire, Duel

A browser-based, three-part intro to **gravity and projectile motion in 2D**. Each mission is built around one idea that students have to *discover* by playing. It runs entirely in the browser, with no install and no accounts.

**▶ Play:** https://tdavidsm.github.io/projectile-missions/

## The three missions

| # | Mission | The big idea | To clear |
|---|---------|--------------|----------|
| 1 | 📦 **Warehouse Drop** | Falling takes time, and more height means more time. So you let go *before* the robot is below you, and *earlier* for higher shelves. | 5 catches in a row |
| 2 | 🏴‍☠️ **Pirate Cannon** | Horizontal and vertical motion are independent. A horizontally-fired ball keeps its sideways speed, so **match the shark's speed** and you hit it from *any* height. | 5 hits in a row |
| 3 | 🏹 **Archer Duel** | Height gives range *and* impact speed. The tower archer out-ranges the ground archer and hits harder. | Win a best of 7 |

Missions unlock in order. Finishing one earns its ★ (saved on the device), and finishing all three gives a **completion code** with the student's initials in the **3rd and 6th** spots.

## How each mission plays

**📦 Warehouse Drop.** The worker climbs to a random shelf (2–16 m drop, never the same twice in a row). The first five shelves are all different and always include one height and its double (2 & 4, 4 & 8, 6 & 12, or 8 & 16 m) so students can compare fall times in their log while a robot rolls in at a steady 3.0 m/s. Students tap **DROP** (or tap the scene / press Space). A floor ruler shows the robot's distance from the drop line. After each drop you see the fall time, the lead distance that was needed (`v × t`), where they actually let go, and a 0.1 s strobe of the falling box. A miss resets the streak.

**🏴‍☠️ Pirate Cannon.** The cannon only fires horizontally, from a random gun deck (3–13 m). Students set only the **launch speed** (0.5 m/s steps). The shark (3–10 m/s, shown) swims out from under the ship, and the cannon fires automatically the instant it passes below. Dotted strobe lines connect ball and shark at the same moments. When the speeds match, the lines are vertical. Height and shark speed both change every shot.

**🏹 Archer Duel.** 15 m tower, 25 m/s bow limit, any angle. Students aim by **dragging on the scene** (direction = angle, length = speed) or with steppers. Players take turns, and the ground archer may walk up to 8 m per turn. Roles swap every round: the student is on the tower in rounds 1, 3, 5, 7.
- **Damage = 1.5 × impact speed.** Tower arrows speed up on the way down (≈30 m/s → ~45 damage). Ground arrows slow down on the way up (≈18 m/s → ~28 damage).
- From the tower the range is ~77 m. From the ground you must be within ~46 m to reach the top of the tower. The ground archer starts ~71 m out, so they're under fire before they can shoot back.
- The **computer's accuracy is randomized and tightens with every shot it takes in a round** (angle and speed noise shrink by 40% per shot).
- Each round-end screen includes a "Did you notice?" note on range or impact speed.

## Reflection questions
After each mission, students answer **3 questions** (80–400 characters each) before the next mission unlocks. On the last mission they answer before getting the code. Drafts autosave on the device. A built-in checker (no library) blocks keyboard mashing, non-words, word salad, repeated words, copying the question, reusing another answer, and off-topic filler. It does **not** judge whether an answer is correct. All 9 answers go to the Google Form together with the name and completion code.

| Mission | Questions |
|---|---|
| 📦 Drop | Why let go *before* the robot is under you? · How did timing change with height (use your log)? · Did 4× the height give 4× the fall time, and what does that say about speed while falling? |
| 🏴‍☠️ Cannon | What speed always hit, and why? · What happened to the horizontal speed, and what was gravity doing? · Twice as high, same speed: still a hit? What changes and what stays the same? |
| 🏹 Duel | Tower or ground: which had the advantage (2 reasons)? · Why do tower arrows hit harder (gravity going up vs. down)? · How did angle and speed changes move the arrow's path? |

**Google Form setup:** 11 questions: Name, Completion code (Short answer), then M1Q1–M3Q3 (Paragraph). Make a pre-filled link with the placeholders `NAME, CODE, M1Q1 … M3Q3` typed into the matching questions, and paste it into `FORM_PREFILL_LINK` in `index.html`. The entry IDs are read automatically. (Google rejects pre-filled links over about 8,000 characters. The longest possible submission here is about 4,500.)

## Teaching notes
- Every attempt goes into a **log** under the scene (height, lead distance, speeds, miss distance, impact speed, damage) for spotting patterns and for debriefs.
- g = 9.8 m/s², no air resistance.
- **🔑 Teacher unlock:** passcode **1253** unlocks every mission on that device until the page reloads (handy for demos). It does not award the completion code.
- Built touch-first for **iPad Safari**, and also works on Chromebooks and laptops.

## Tech
A single self-contained `index.html`: plain HTML/CSS/JS, canvas animation, no dependencies. Deploy with GitHub Pages from `main`.
