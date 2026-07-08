# Weekly Progress Log

> Update this file **every week**. Add a new entry at the top for each week.
> This is the first thing we check during review. Keep it honest and specific — it also feeds your attendance record (Rule 1).

**How to use:** copy the *Week template* block below for each new week. Newest week goes at the top.

---

## Week template — copy me

### Week N — YYYY-MM-DD

**Attended this week's meeting:** Yes / No (if No, did you email leave? Yes / No)

**Progress this week**
- _What did you actually do / finish?_

**Challenges & blockers**
- _What got in the way? What are you stuck on?_

**Next steps**
- _What will you do next week?_

**Hours spent (optional):** _e.g. 6h_

**Links (optional):** _commits, notebooks, docs, datasets..._

---

<!-- =================  YOUR ENTRIES BELOW  ================= -->

### Week 1 — 2026-06-29

**Attended this week's meeting:** Yes
**Progress this week**
Completed two rounds of MLP model training (Run 7 & Run 8). Model configuration: 30→128→128→6, ELU activation, Gaussian policy.
Run 8 (adaptive lr=1e-4) showed significant improvement over Run 7 (lr=1e-3): Final Reward increased from 43 to 56, survival reward reached the maximum value of 1.0, and Episode Length improved from significant drift to consistently reaching 500 steps.
Completed a 20-second simulated motion performance evaluation:
Forward velocity tracking rate: ~55% (during rotational movements).
Stationary command (0,0,0): Stable standing with no falls.
Posture control: Excellent stability with a maximum roll angle of only 0.15°.
Altitude stability: Z-axis height stabilized at 0.24m with a maximum fluctuation of 0.19m.
Training video has been uploaded to Feishu.
**Challenges & blockers**
Yaw rotation drift: During in-place rotation commands (-0.98 rad/s), the agent exhibits a Y-axis drift of approximately 2.8m per 20s. The angular velocity tracking reward weight (currently 0.5) may be too low.

**Next steps**
Increase the track_angular_velocity reward weight to mitigate yaw drift.
Reduce the flat_orientation_l2 penalty weight (-1.0 → -0.5) to relax posture constraints.
Initiate Run 9 to tune angular tracking weights, or enable Viser web visualization for real-time debugging.
Conduct preliminary real-world testing with the current model in a controlled environment.
**Hours spent (optional):**

**Links (optional):**
