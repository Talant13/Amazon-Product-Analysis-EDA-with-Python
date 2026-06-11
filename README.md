# 🏋️ Gym Members Exercise Tracking — EDA with Python
 
Exploratory Data Analysis on gym member workout data, examining how workout type, BMI, hydration, and gender relate to calories burned and session performance.
 
> 📦 Dataset: [Gym Members Exercise Tracking — Kaggle](https://www.kaggle.com/datasets/valakhorasani/gym-members-exercise-tracking)
 
---
 
## 📁 Dataset
 
**File:** `gym_members_exercise_tracking.csv`  
**Size:** 973 members, 15 columns — no missing values, no duplicates
 
| Column | Type | Description |
|--------|------|-------------|
| `Age` | int | Member age |
| `Gender` | object | Male / Female |
| `Weight (kg)` | float | Body weight |
| `Height (m)` | float | Body height |
| `Max_BPM` | int | Max heart rate during workout |
| `Avg_BPM` | int | Average heart rate during workout |
| `Resting_BPM` | int | Resting heart rate |
| `Session_Duration (hours)` | float | Length of workout session |
| `Calories_Burned` | float | Calories burned per session |
| `Workout_Type` | object | Yoga / HIIT / Cardio / Strength |
| `Fat_Percentage` | float | Body fat % |
| `Water_Intake (liters)` | float | Daily water intake |
| `Workout_Frequency (days/week)` | int | Sessions per week |
| `Experience_Level` | int | 1 = Beginner, 2 = Intermediate, 3 = Advanced |
| `BMI` | float | Body Mass Index |
 
---
 
## 📊 Analysis & Findings
 
### 1. Distributions
- **Weight** is right-skewed — most members cluster between 50–90 kg with a long tail toward heavier weights
- **Calories burned** is roughly bell-shaped, centered around ~900 kcal/session
- **BMI** is right-skewed, with most members in the normal-to-overweight range
- **Workout types** are evenly distributed — no single activity dominates the dataset
### 2. Calories Burned & BMI by Workout Type
- **Strength training** burns the most calories on average, followed by Cardio, HIIT, and Yoga
- **BMI is nearly identical across all workout types** (~24–25) — members self-select into activities regardless of body composition
### 3. Calorie Burn by Gender & Workout Type
- Male and female calorie burn distributions **overlap almost completely** across all 4 workout types
- No meaningful gender gap — gender does not predict how many calories are burned
### 4. Session Duration by Workout Type
- Average session duration is **similar across all workout types** (~1.1–1.4h)
- Very few outliers — suggesting structured, consistent workout sessions across the board
### 5. Water Intake vs. Calories Burned
- **No clear correlation** — scatter plot shows a diffuse cloud with no visible trend
- Hydration levels don't predict calorie burn in this dataset
### 6. BMI vs. Calories Burned by Gender
- **No trend between BMI and calories burned** for either gender
- Both male and female data points are scattered uniformly — BMI is not a predictor of workout output
---
 
## 🔑 Key Takeaways
 
| Finding | Insight |
|---------|---------|
| Strength > Cardio > HIIT > Yoga | Workout type is the strongest predictor of calories burned |
| BMI flat across workout types | Members don't choose workouts based on body composition |
| Gender gap is negligible | Male and female members burn similar calories per session |
| Water intake ≠ calorie output | No hydration-performance relationship visible in the data |
| Consistent session durations | All workout types average ~1.1–1.4h with low variance |
 
---
 
## 🛠️ Tech Stack
 
- **Python 3.x**
- `pandas` — data loading and summary statistics
- `matplotlib` — scatter plots, bar charts, box plots
- `seaborn` — histograms, KDE plots, FacetGrid, countplots
---
