# Spotify Streaming Behavior Analysis

Analyzed 100K+ Spotify streaming records using SQL (PostgreSQL) to quantify how shuffle mode, platform type, and time-of-day affect track completion rates and user engagement. Shuffle users skip 54% of tracks vs. 28% unique track variety in non-shuffle, and Mac users complete 90.39% of tracks compared to 35.16% on the web player.

---

## Business Questions

- Does shuffle mode reduce engagement or track variety?
- Which platforms drive the highest and lowest completion rates?
- When are users most active, and does it vary by platform?
- Which artists and songs dominate peak listening hours?

---

## Dataset

| Property | Detail |
|----------|--------|
| Source | Personal Spotify streaming history export |
| Records | 100,000+ streaming events |
| Fields | Track name, artist, platform, playback duration, shuffle flag, skip flag, timestamp |
| Dictionary | See `spotify_data_dictionary.csv` |

---

## Key Findings

### 1. Shuffle Mode Drives Repetition and Skipping
- Shuffle users play only **9.95% unique tracks** vs. **28.07%** in non-shuffle (nearly 3x less variety)
- **54.03% of shuffled tracks are skipped** before completion, pointing to algorithm-preference mismatch
- Shuffle mode likely surfaces tracks outside the user's active preference window

### 2. Platform Predicts Engagement More Than Time of Day
- **Mac** users: 90.39% completion rate, 3.67 min avg playback (highest engagement)
- **Web player** users: 35.16% completion, 2.34 min avg playback (lowest engagement)
- **Android** users: highest raw volume (107,754 plays) but heavily shuffle-dependent with high skip rates
- Platform-specific UX likely influences listening intent, focused vs. background

### 3. Listening Peaks Are Platform-Specific
- **Android** peaks at midnight (10,443 plays), late-night passive listening
- **iOS** peaks 6 to 9 PM, active evening sessions
- **Casting devices** peak 5 to 6 PM, likely home or social listening
- **Web/Windows** users peak at 1 AM and 6 AM, background music during work or study

### 4. Peak-Hour Content Is Genre-Consistent
- Alternative and soft rock dominate peak hours across platforms
- Top artists: The Killers, Jimmy Eat World, John Mayer, Ed Sheeran
- Most played track during peak hours: *Dying Breed* by The Killers

---

## Product Hypotheses (If Applied at Scale)

These findings, if validated against a full user base, would suggest:

1. **Shuffle algorithm improvement**: weight recently skipped tracks lower in the shuffle queue to reduce repeat-skip cycles
2. **Platform-specific autoplay logic**: web player users show low completion, so "Continue Listening" nudges could recover engagement
3. **Peak-hour personalization**: push genre-consistent recommendations during each platform's peak window rather than generic trending content
4. **Completion-rate as a ranking signal**: track completion % is a stronger engagement proxy than play count for playlist curation

---

## Technical Approach

| Skill | Application |
|-------|-------------|
| Window Functions | Ranked tracks by play count within peak hour windows |
| CTEs | Modularized multi-step engagement calculations |
| Aggregations | Platform-level completion rate, avg playback duration |
| Indexing | Optimized query performance by 30%+ on large scans |
| Data Cleaning | Handled null durations, deduped streaming events |

---

## Files

| File | Description |
|------|-------------|
| `spotify_history.csv` | Raw streaming dataset |
| `spotify_data_dictionary.csv` | Column definitions and data types |
| `spotify_analysis.sql` | All queries, organized by analysis section |

---

## How to Run

```sql
-- 1. Create a PostgreSQL database
-- 2. Import spotify_history.csv into a table named `spotify_history`
-- 3. Run spotify_analysis.sql section by section
-- Tested on PostgreSQL 15+
