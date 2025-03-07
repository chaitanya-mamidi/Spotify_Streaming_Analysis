
# 🎵 **Spotify Streaming Analysis**  

## **📌 Project Overview**  

Music is a part of our daily lives, and streaming platforms like **Spotify** generate tons of data on **how, when, and where** people listen.  

This project **dives into real user listening behavior** using **SQL (PostgreSQL)** to uncover:  
✔️ How shuffle mode impacts track variety and engagement  
✔️ The most active platforms and their listening trends  
✔️ What time of day people listen the most  
✔️ Which songs dominate peak streaming hours  

Everything is done **purely in SQL**, making this a great **database-focused analysis** showcasing raw data exploration skills.  

---

## **📂 Files in This Repository**  

| File | Description |
|------|------------|
| `spotify_history.csv` | The actual dataset—Spotify streaming history, including track details, playback time, platform, and shuffle usage. |
| `spotify_data_dictionary.csv` | A simple data dictionary explaining what each column means. |
| `spotify_analysis.sql` | A collection of **SQL queries** that drive the entire analysis. |

---

## **🔍 Key Insights**  

### 🎛 **1. Shuffle Mode Leads to More Repetition & Skipping**  
- When **shuffle mode is on**, users play a **smaller variety of unique tracks (9.95%)** compared to non-shuffle mode (**28.07%**).  
- **More than half (54.03%) of shuffled songs are skipped before finishing**, showing that shuffle often plays tracks that users don’t want at that moment.  

### 📱 **2. Platform Usage Matters**  
- **Android users rely on shuffle mode the most (107,754 plays),** but their **engagement is lower**, meaning they skip a lot.  
- **Mac users have the highest track completion rate (90.39%) and longest playback time (3.67 min),** while **web player users have the lowest engagement (35.16% completion, 2.34 min playback).**  

### ⏳ **3. When Are People Streaming the Most?**  
- **Android peaks at midnight (10,443 plays), iOS is busiest in the evening (6-9 PM), and casting devices peak in early evenings (5-6 PM).**  
- **Web and Windows users mostly listen in the early morning (1 AM, 6 AM),** possibly for background music while working or studying.  

### 🎶 **4. What Songs Dominate Peak Hours?**  
- **Alternative & soft rock dominate peak listening hours,** with **The Killers, Jimmy Eat World, John Mayer, and Ed Sheeran** among the top artists.  
- **"Dying Breed" by The Killers** was played the most during peak hours.  

---

## **🚀 Recommendations**  

📌 **1. Improve Shuffle Mode to Increase Engagement**  
- Enhance **Spotify’s shuffle algorithm** to prioritize user preferences and avoid too much repetition.  
- Introduce **“Smart Shuffle”**, which learns what users skip and adjusts track selection dynamically.  

📌 **2. Optimize the Experience Across Platforms**  
- Mobile (Android, iOS): Reduce playback interruptions by refining autoplay algorithms.  
- Web Player: Improve engagement by suggesting **“Continue Listening”** playlists for unfinished tracks.  

📌 **3. Leverage Peak Listening Hours**  
- Push personalized recommendations **at peak hours** when engagement is highest (late night for Android, evenings for iOS).  
- Introduce **dynamic playlists** based on real-time activity.  

📌 **4. Personalize Playlists Based on User Behavior**  
- Instead of static genre-based playlists, create **AI-driven recommendations** that adjust to user listening habits over time.  

📌 **5. Implement a More Dynamic Playback Experience**  
- Introduce **mood-based auto-mixes** that create seamless transitions based on what users are already enjoying.  
- Reduce **abrupt skips** by allowing users to fine-tune what they want to hear without fully changing the queue.  

---

## **📌 Skills Used in This Project**  
✅ **SQL (PostgreSQL)** – Advanced queries, aggregations, window functions, CTEs  
✅ **Data Cleaning & Transformation** – Working with raw streaming data  
✅ **Exploratory Data Analysis (EDA)** – Identifying meaningful trends  
✅ **Data Storytelling** – Translating raw data into insights & recommendations  

---
## **🔍 Conclusion**  

This project explores **Spotify streaming behavior** using SQL, revealing insights into **shuffle mode impact, platform engagement, peak listening times, and track popularity.** The findings highlight **how user habits influence music consumption** and provide **data-driven recommendations to enhance playback experiences.** It showcases the power of **SQL-driven analysis in understanding user behavior and optimizing digital streaming platforms.**
