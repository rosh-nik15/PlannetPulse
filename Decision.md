# Product Decisions

## DP1 · The Nudge

**Question:** What should the app do when the weekly target is crossed?

**Decision:** The app should warn and encourage the user, but it should never shame or block them.

**Why:** The purpose of PlanetPulse is to help users understand their impact and make better choices. Going over the target should not make the user feel punished.

**How it works:**

* Show a clear message that the weekly target has been crossed.
* Show the user's current CO₂ value and the target.
* Keep the message neutral and simple.
* Suggest possible lower-impact choices.
* Let the user continue using the app normally.

**Reliability:** The app should inform the user about the result instead of trying to force their behavior.

---

## DP2 · Absurd Input

**Question:** What should happen if someone enters an obviously wrong value, such as 500,000 km for a car trip?

**Decision:** The app should reject clearly unreasonable values and ask the user to check the entry.

**Why:** A wrong value can make the total carbon footprint extremely inaccurate and affect all the dashboard results.

**How it works:**

* Check the value before saving it.
* Reject values that are clearly unrealistic.
* Tell the user why the value needs to be checked.
* Never silently change the value entered by the user.
* If a value is unusually high but could still be real, ask for confirmation instead of immediately rejecting it.

**Example:**

`500,000 km → "This distance seems unusually high. Please check your entry."`

**Reliability:** This keeps incorrect data out while still giving users control over valid unusual entries.

---

## DP3 · The Week

**Question:** When should a week start, and how should progress be shown during the week?

**Decision:** PlanetPulse will use a Monday–Sunday week.

**Why:** Using a fixed weekly cycle makes the progress easier to understand and keeps weekly comparisons consistent.

**How it works:**

* The week starts on Monday.
* The week ends on Sunday.
* The dashboard shows the current week's date range.
* Progress is based only on activities recorded during the current week.
* The app shows the current CO₂ total compared with the weekly target.
* A new weekly calculation starts every Monday.
* Previous weeks remain available in history.

**Example:**

`Wednesday → 3.2 kg / 5 kg → 64% of weekly target`

**Reliability:** The app should calculate the week from the activity date, so activities are always counted in the correct week.

---

## General Reliability Principle

PlanetPulse should be simple, clear, and predictable.

* Warn users instead of punishing them.
* Check unusual inputs instead of silently changing them.
* Keep calculations understandable.
* Keep user activity records visible.
* Use the same rules consistently.
* Explain why an input is rejected.
* Let users correct their own mistakes.

