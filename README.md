# 🎵 Music Virality Analysis: What Makes Songs Go Viral?

## 📖 Project Overview

A comprehensive data analysis investigating the factors that drive music success in the streaming era. Using a dataset of over 20,000 songs, this project examines licensing, video content, platform strategies, and audio features to decode the patterns behind viral hits.

**Key Question:** What separates viral hits from forgotten tracks in today's music landscape?

## 🎯 Business Problem

With over 100,000 songs uploaded to Spotify daily, artists and labels need data-driven insights to understand what drives streaming success. This analysis provides actionable intelligence for music industry stakeholders.

## 📊 Dataset

- **Source:** Songs dataset from Hugging Face
- **Size:** ~20,000 tracks
- **Features:** Artist, Track, albums, duration, channel, Audio characteristics (danceability, energy, tempo), licensed, video, streaming metrics, engagement data

## 🔬 Research Hypotheses

This analysis tests five key factors that may influence song success:

1. **Licensing Status:** Do licensed tracks outperform unlicensed ones?
2. **Video Content:** Does having an official music video boost performance?
3. **Platform Strategy:** Which streaming platforms drive the most success?
4. **Song Duration:** Is there an optimal song length for virality?
5. **Audio Features:** Do specific characteristics (energy, danceability, tempo) predict hits?

## 📏 Success Metrics

**Hit Definition:** Songs in the top 20% for either metric
- **Engagement Ratio:** (Likes + Comments) ÷ Views
- **Stream Count:** Raw streaming numbers

**Song Categories:**
- **Hits:** High streams + High engagement
- **Shallow:** High streams + Low engagement (viral but not sticky)
- **Hidden Gems:** Low streams + High engagement (niche but loved)
- **Flops:** Low streams + Low engagement
- **Normal/Mid:** Everything else (majority of tracks)

## 🛠️ Technical Stack

- **SQL (BigQuery):** Data cleaning, aggregation, segmentation, Hypothesis testing, Correlation analysis
- **Python:** Audio feature analysis, statistical modeling, visualization
  - pandas, numpy, matplotlib, seaborn
- **Excel:** Exploratory Data Analysis

## 📈 Key Findings

### 1. Licensing Impact
- Licensed tracks: **60% higher streams** (150.5M vs 94.2M average)
- Unlicensed tracks: **12% higher engagement ratio** (deeper fan connections)

### 2. Video Effect
- Official videos provide **70% stream boost** (147.3M vs 86.4M)
- No impact on engagement quality (same engagement ratios)

### 3. Platform Dynamics
- **YouTube:** 800x higher streams per song despite fewer tracks in dataset
- **Spotify:** Superior engagement ratios and listener loyalty

### 4. Audio Feature Patterns
- **Hit Songs:** Balanced across all features (moderate energy, controlled loudness)
- **Failed Tracks:** Extreme values (too acoustic, too live, unbalanced production)
- Individual features show weak correlation with success (-0.1 to +0.1)

### 5. Duration Insights
- Song length shows **zero predictive power** for success
- Short + danceable tracks: High streams but lower engagement
- Execution matters more than duration


## 📋 Methodology

### Phase 1: Data Preparation
- Cleaned 20K records, handled missing values
- Created engagement ratio metric
- Segmented songs into success categories

### Phase 2: SQL Analysis
- Licensing and video impact analysis
- Platform performance comparison
- Duration-based segmentation
- Artist and track ranking systems

### Phase 3: Python Deep-Dive
- Correlation analysis between audio features and success
- Visualization of key patterns

### Phase 4: Business Intelligence
- Stakeholder-ready insights
- Strategic recommendations by user type

## 💡 Strategic Recommendations

### For Independent Artists
- Focus on Spotify for fan development
- Consider strategic unlicensed releases for core audience
- Prioritize engagement over raw streams

### For Record Labels
- Invest in music videos (70% stream multiplier)
- Secure licensing for mainstream distribution
- Use YouTube for viral reach, Spotify for retention

### For Music Producers
- Target balanced audio profiles
- Avoid extreme values in any single feature
- Moderate loudness (~-7dB) outperforms compression



