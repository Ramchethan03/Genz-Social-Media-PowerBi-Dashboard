# 📊 Global GenZ Engagement & Well-being Tracker

An enterprise-grade, multi-page Power BI dashboard analyzing behavioral platform dynamics, multi-homing trends, and digital well-being metrics across 1,000,000 simulated GenZ profiles.

## 🔗 Live Interactive Link
👉https://app.powerbi.com/groups/me/reports/024a4d03-b522-4f49-960a-45882e7195a1/bae4cd92494117704c45?experience=power-bi

## 🛠️ Data Architecture & Key Features
- **Data Volume:** 1,000,000 transaction records normalized into clean star-schema profiles.
- **Power Query Pipeline:** Engineered conditional logic categories separating cohorts into Early Teens, Late Teens, Young Adults, and Adults.
- **Advanced UX Elements:** Implemented high-density vertical navigation drawers, state-dependent dynamic Tile Slicers, and report-page tooltip configurations.

#DAX MEASURES:
=>1. Core Cohort Count
Total Users = COUNTROWS('genz_social_media_usage')
=>2. Average Daily Usage Format
Avg Daily Usage Hours = AVERAGE('genz_social_media_usage'[daily_usage_hours])
=>3. Night Engagement Percentage
Night Usage % = 
DIVIDE(
    CALCULATE([Total Users], 'genz_social_media_usage'[night_usage] = 1),
    [Total Users],
    0
)
=>4. High Addiction Prevalence Rate
High Addiction % = 
DIVIDE(
    CALCULATE([Total Users], 'genz_social_media_usage'[addiction_level] = "High"),
    [Total Users],
    0
)
=>5. Dynamic Mental Health Indicator
Avg Mental Health Score = AVERAGE('genz_social_media_usage'[mental_health_score])
=>6. Conditional Color Formatter for Mental Health KPI 
Mental Health Color Format = 
IF([Avg Mental Health Score] < 5, IF([Avg Mental Health Score] < 7.5))

# 📁 Dashboard Structure & Visual Matrix

### 📱 Page 1: Executive Overview (Demographics & Market Share)
*Focuses on global cohort scale, platform dominance, and core population traits.*
* **KPI Metrics:** Total Cohort ($1,000,000$), Avg. Daily Usage ($3.51\text{ hrs}$), Multi-Homing Index ($3.00\text{ platforms}$), Nocturnal Activity Ratio ($60.00\%$).
* **Market Share:** Horizontal bar chart demonstrating **Instagram** as the top primary platform, followed closely by **YouTube** and **TikTok**.
* **Geographics & Demographics:** A dark-themed global map tracking multi-nation footprint density alongside a clean breakdown of gender and age groupings.

### 🔄 Page 2: Behavioral Insights (Platform Dynamics & Intent)
*Deconstructs user intent, session stickiness, and platform dependency concentrations.*
* **Intent Tracking:** Clustered columns proving **Entertainment** and **Socializing** dominate usage goals over news or education.
* **Stickiness Matrix:** Scatter plot mapping daily usage hours against individual session depths to highlight cluster trends.
* **Addiction Concentration:** A clean Treemap segmenting the cohort into High, Medium, and Low risk blocks.

### 🧠 Page 3: Well-being Metrics (Digital Health & Impact)
*Our deep-dive "Insight Page" establishing correlations between usage patterns and mental health.*
* **Risk Heatmap:** Matrix table mapping `addiction_level` against night usage, uncovering a sharp decline in mental health scores for heavy midnight users.
* **Screen Time Impact Chart:** Combo line/column visual proving mental health baselines decline linearly as pre-sleep screen exposure increases.
* **Prevalence Gauge:** High-impact dynamic circular gauge tracking high-risk profile concentrations.

