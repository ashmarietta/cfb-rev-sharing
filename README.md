# Power vs. Mid-Major Gap in College Football: Competitive Balance, Revenue, and Recruiting
This is a reproducible sports analytics project examining whether the first season of NCAA revenue-sharing (effective July 1, 2025, per the House v. NCAA settlement) coincides with an early, measurable shift in the gap between Power Four and mid-major FBS football programs.
The analysis combines CollegeFootballData.com (CFBD) team, game, recruiting, and transfer portal data with Knight-Newhouse College Athletics Database revenue data, covering 534 classified FBS team-seasons.

---

## Project Objectives
This project investigates two research questions:
1. **Competitive balance and revenue:** Did the win percentage gap, bowl appearance rate gap, and revenue gap between power and mid-major programs change in the first revenue-sharing season (2025) relative to the three prior seasons (2022–2024)?
2. **Recruiting outcomes:** Is there an early, measurable difference in recruit distribution and transfer portal flow between tiers in the first cohort recruited under revenue-sharing (2026 class) vs. the three prior classes (2023–2025)?

Key business questions:
1. As revenue sharing reshapes how programs fund rosters, is the on-field and financial gap between power and mid-major programs widening, holding steady, or narrowing?
2. Does recruiting behavior show the same pattern?

---

## Data Sources
1. CollegeFootballData.com (CFBD) API — team/conference records, game results, recruiting rankings, transfer portal entries
2. Knight-Newhouse College Athletics Database (knightnewhousedata.org) — tier-level median athletic department revenue and expenses
3. Sports Reference — secondary check on team and conference records

**Data limitation:** Revenue is only available at the tier level (power, mid-major, all-FBS median), not by conference or by individual school. 2025 revenue figures also include new categories (institutional NIL revenue-share, restructured athletic student aid) tied to the settlement that don't exist in 2022–2024 data, so 2025 is treated as a distinct post-settlement data point rather than blended into prior trends.

---

## Methodologies
The following steps were implemented in Python in Google Colab, plus a supplementary Excel workbook for the revenue/competitive-balance analysis:
1. Team/conference tier classification, with manual handling of realignment edge cases
2. Win percentage and postseason appearance rate computed per team-season and averaged by tier and year
3. Tier-level revenue and expense medians merged in by year from the Knight-Newhouse database
4. Gap metrics computed year-over-year for win percentage, bowl rate, and revenue with 2025 compared against the 2022–24 average as the pre-settlement baseline
5. Groupby/pivot aggregation of recruiting class composition by star rating and tier by year
6. Groupby/pivot aggregation of transfer portal flow by origin tier and destination tier by year
7. Percentage-share and gap calculations for recruiting by year
8. Visualization of all trends with 2025 (competitive balance/revenue) and 2026 (recruiting) flagged as the first data points under revenue-sharing

---

## Key Findings
### 1. The Win Percentage Gap Has Stayed Remarkably Stable, Including Through the First Revenue-Share Season
* Power programs' average win percentage held in a tight band. It was 56.3%–56.7%, across all four seasons, while mid-major programs averaged 47.6%–48.2%.
* The resulting gap barely moved, and there was no meaningful shift from the 2022–24 average (8.6 points) in the first revenue-sharing season.

---

### 2. The Bowl/CFP Appearance Rate Gap Widened for Three Years but Nearly Vanished in 2025
* The bowl-rate gap grew from 13.2 points (2022) to 13.4 (2023) to a four-year high of 19.1 points (2024).
* It then collapsed to just 2.9 points in 2025, while power programs' bowl rate fell from 70.6% to 61.8% and mid-major's rose from 51.5% to 58.8%.

---

### 3. The Financial Gap Widened Sharply in Revenue-Sharing's First Year
* Median power-program revenue jumped from $153.5M (2024) to $178.5M (2025) — about 16% growth, versus roughly 5% and 2% year-over-year growth in the two prior years.
* Mid-major revenue grew more modestly, from $43.8M to $48.4M.
* The dollar gap between tiers grew from $109.7M (2024) to $130.1M (2025), which was its largest single-year jump in the dataset.

---

### 4. Year One of Revenue Sharing: The Financial Gap Grew, but the Competitive Gap Didn't
* Despite the largest financial-gap increase in the four-year window, 2025 didn't produce a wider competitive gap. The win percentage gap barely moved, and the bowl-rate gap narrowed.
* One post-settlement season isn't enough to call this a trend. It's an early signal that money and on-field competitiveness aren't moving in lockstep yet, which could be worth re-checking after the 2026 season.

---

### 5. The FBS Landscape Splits Nearly Evenly Into Power and Mid-Major with a Sizable Gray Zone
* 270 team-seasons classified as power, 264 as mid-major (2022–2025) — a nearly even split
* 170 transfer entries had an unclassifiable origin and 187 an unclassifiable destination, pointing to a consistent volume of movement involving non-FBS or otherwise unclassified programs

---

### 6. Top Transfer Destinations Shift Every Year Across Both Tiers
* The most popular transfer destinations change year to year and mix power and mid-major programs. Colorado, Louisville, and Purdue (power) and Texas State (mid-major) all appear among the top destinations in a given year.

---

### 7. The Mid-Major-to-Power Transfer Pipeline Is Accelerating
* 3+ star transfers from mid-major to power programs more than doubled from 183 (2023) to 460 (2026).
* Movement between power programs also grew substantially from 515 to 837 3+ star transfers.
* Power-to-mid-major transfers rose, too, from 310 (2023) to 499 (2026) and peaking at 527 in 2025.
* Movement within the mid-major tier peaked at 424 in 2025 before dipping to 360 in 2026.

---

### 8. The 3+ Star Recruiting Gap Is Narrowing
* Power's share of the overall 3+ star class fell from 53.4% (2023) to 45.2% (2026).
* Mid-major's share rose from 28.3% to 37.4% over the same span.
* The power-minus-mid-major gap narrowed from 25.2 points (2023) to 7.8 points (2026).

---

### 9. Elite (4-/5-Star) Recruiting Remains an Almost Total Power Monopoly
* Power programs signed 98–99% of all 4-and-5-star recruits in every year studied; mid-major programs never exceeded 1.4% of that pool in any year.
* Mid-major programs signed zero 5-star recruits in any year.

---

### 10. The First Revenue-Share Cohort (2026) Shows Continuity, Not a Break, on the Recruiting Side
* The 3+ star gap-narrowing trend and elite-tier power dominance both continued through 2026 without an abrupt shift.
* One post-settlement recruiting class isn't enough to say revenue sharing caused the narrowing. The trend line was already moving this direction before July 2025, but it also hasn't reversed or stalled.

---

## Strategic Implications
### For Mid-Major Programs
* The narrowing 3-star recruiting gap and growing inbound transfer volume from power programs (499 transfers in 2026) suggest real opportunity to build competitive rosters through the portal and mid-tier high school recruiting.
* The narrowing in bowl-rate gap in 2025 is an encouraging signal, as it arrived in the same year the revenue gap widened the most.

---

### For Power Programs
* Revenue growth in 2025 (~16% YoY) outpaced any movement in competitive balance. The spending advantage hasn't yet translated into a wider on-field gap.
* Rising intra-power transfer volume (837 in 2026) indicates the portal is becoming as central to roster construction as high school recruiting.
* Ceding ground on 3-star recruits may be a rational tradeoff if it frees resources to protect the 4-/5-star pipeline, where dominance remains nearly absolute.

---

### For Administrations
* The mismatch between the widening financial gap and the flat competitive gap in 2025 is a useful signal that revenue and on-field performance don't necessarily move in lockstep in the short term.
* A single post-settlement season/cohort can't support causal claims about revenue sharing's effect on competitive balance or recruiting.
* Bowl rate is a small-sample, binary metric, and one should treat 2025's sharp swing as a data point to monitor, not a confirmed trend, until a second post-settlement season is available.
* Tracking the 2026 season and 2027–2028 recruiting classes will show whether these are continuations of existing trends or genuine inflection points.

---

## Repository Contents
* `fbs_gap.ipynb` — Full data pull, tier classification, and recruiting/transfer portal analysis workflow
* `fbs_gap.html` — Exported notebook with all code blocks, outputs, and visualizations
* `fbs_gap_revenue_analysis.xlsx` — Win-loss, bowl-rate, and Knight-Newhouse revenue data by tier and year with gap-trend calculations and charts
* Visualizations: power vs. mid-major win percentage, bowl rate, and revenue by year; power vs. mid-major share of 3+ and 4+/5-star recruiting classes

---

## Final Insights
After year one of revenue sharing, the money moved before the competition did. The financial gap between power and mid-major programs widened more sharply in 2025 than in any prior year in this dataset; however, win percentage barely budged, and the bowl-rate gap actually shrank to its smallest point in four years. On the recruiting side, the story is more continuous. The narrowing 3-star and transfer-portal gap between tiers was already underway before the settlement and continued into the first revenue-share recruiting class, while the very top of the board remains almost entirely to the power conferences. Whether the financial gap eventually pulls the competitive and recruiting gaps along with it will only be visible with another two or three years of data.

---
