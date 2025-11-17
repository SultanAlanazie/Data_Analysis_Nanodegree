# Ford GoBike System Data Exploration

## by Sultan Alanazi

## 📘 Dataset Overview

This project explores the **Ford GoBike (Bay Wheels) system dataset**, which contains detailed information about over 160,000 bike-share trips recorded across the San Francisco Bay Area.

After data cleaning and transformation, the final dataset includes:

- **160,184 rows** and **21 features**
- Trip details (duration, start/end locations, timestamps)
- Membership information (Subscriber vs Customer)
- Rider demographics (age, gender)
- Engineered time-based variables (start hour, weekday)
- Engineered duration formats (minutes, hours)

### **Data Source**

The dataset originates from the official Ford GoBike/Bay Wheels bike-share system.

### **Wrangling & Cleaning Steps**

Before beginning the analysis, several steps were taken to prepare the dataset:

- Removed missing and invalid demographic entries
- Converted timestamps to datetime formats
- Engineered new variables:
  - `member_age`, `duration_minute`, `duration_hour`
  - `start_hour`, `weekday`
- Removed unrealistic ages (caused by incorrect birth years)
- Converted text features to categorical types
- Ensured consistent, tidy formatting

The resulting dataset is clean, well-structured, and suitable for exploratory and explanatory analysis.

## 📊 Summary of Findings

### **Univariate Findings**

- Rider ages cluster mainly between **25–35 years**, forming a clean unimodal distribution.
- Trip duration is **right-skewed**: most rides last **5–10 minutes**, with a long tail toward longer durations.
- **Subscribers** account for the vast majority of rides.
- The gender distribution is dominated by **Male** riders, followed by **Female**, with **Other** representing a small minority.

### **Bivariate Findings**

- Trip duration patterns are generally similar across genders, but Females and Other riders show slightly **greater variability**.
- **Subscribers** show strong commute patterns, peaking at **8 AM** and **5–6 PM**.
- **Customers** use the service more between **10 AM–5 PM**, indicating leisure-driven usage.
- Customers consistently take **longer trips** than Subscribers across weekdays and weekends.

### **Multivariate Findings**

- **User Type is the strongest predictor** of trip duration:  
  Customers ride longer and with more variability than Subscribers across **every age group, gender, time of day, and day of week**.
- Gender has little effect on trip duration; differences arise mainly from user type.
- Early morning hours show the **highest trip durations**, particularly among Female and Other riders.
- Start and end station coordinates are strongly correlated, but **geography does not influence trip duration**.

### **Overall Conclusion**

The dataset reveals two very distinct usage profiles:

- **Subscribers** ride short, consistent trips tied to commuting.
- **Customers** ride longer, more flexible trips aligned with leisure activities.

Membership category, not demographic or geographic variables, is the primary factor shaping trip duration.

## 🎯 Key Insights for the Presentation

The following insights were selected and polished for the explanatory slide deck:

### **1. Subscriber vs Customer Behavior**

Subscribers display clear **commute-based patterns**, while Customers make **longer, leisure-oriented trips**.

### **2. Gender vs Duration**

Trip durations across genders are similar, with small differences only in variability.

### **3. Time-of-Day Impact**

Peak ridership occurs at traditional **commute hours**, while off-peak periods show longer, more variable trips.

### **4. Weekday vs Weekend Patterns**

Subscribers remain consistent across the week, while Customers ride longer on weekends.

### **Design Improvements for the Slide Deck**

- Simplified visual encodings to emphasize key comparisons (e.g., Subscriber vs Customer)
- Polished titles, labels, legends, and annotations
- Removed grid noise and unnecessary plot elements
- Highlighted only the most meaningful insights to support a clear narrative

## 📁 Repository Structure

- `Part_I_exploration.ipynb` — full exploratory analysis
- `Part_II_slide_deck.ipynb` — explanatory presentation
- `README.md` — summary and key insights
- `dataset/` — contained the raw and the cleaned data

## ✔️ Final Note

This analysis provides a complete end-to-end investigation of the Ford GoBike dataset, combining rigorous data exploration with a clear, structured explanatory narrative supported by refined visualizations.
