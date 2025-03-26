# Meal-Recommender-System

### Authors
Du Duong | Elliot Ly | Daniel Saakian | Jim-Lee Wu

## Overview
The Meal Recommender System is designed to generate personalized daily meal plans based on a user’s nutritional needs, fitness goals, and dietary restrictions. By integrating nutritional calculations with machine learning techniques, the system refines meal recommendations to align with individual requirements.

## Data
- **Source:** Recipe dataset from [Kaggle](https://www.kaggle.com/code/hsggskbsbsjsjkk/diet-recommendation-system/input) with over 500,000 recipes across 312 categories.
- **Data Cleaning:**  
  - Removed irrelevant columns (e.g., author info, non-essential recipe details).  
  - Converted total cook times from "PT#H#M" to minutes.  
  - Filtered recipes by calorie range (300–2000 calories) and cook time (≤400 minutes).  
  - Parsed list-based variables (Keywords, RecipeIngredientQuantities, RecipeIngredientParts) for further analysis.
  - Integrated allergen information to help filter out recipes with user-specified allergens.

## Methods
1. **Nutritional Calculations:**
   - **BMI, BMR, & TDEE:** Calculated using user inputs (weight, height, age, sex, and activity level) to determine daily energy needs.
   - **Macronutrient Distribution:** Derived target ranges for calories, protein, carbohydrates, and fats based on fitness goals (weight loss, muscle gain, or maintenance).

2. **Meal Filtering & Modeling:**
   - **Nutritional Filtering:** Selected recipes whose nutritional values fall within 80% to 120% of the user’s targets, while excluding those with allergens.
   - **K-Nearest Neighbors (KNN):** Standardized nutritional features (Calories, Protein, Fat, Carbohydrates) were used to identify 10 recipes closest to the user’s nutritional requirements.
   - **Ingredient Refinement:** Applied TF-IDF and cosine similarity on recipe ingredient lists to rank and recommend the top 3 meals.

## Results & Analysis
- **Testing:** Evaluated the system with various user profiles (e.g., weight loss, muscle gain, maintenance) to ensure that recommended meals match target nutritional ranges.
- **Visualization:** Conducted exploratory data analysis (EDA) to examine calorie distributions, nutrient correlations, and allergen impacts.
- **Insights:** The system effectively met macronutrient targets; however, one test case revealed challenges with accurately filtering allergens, indicating an area for future improvement.

## Conclusion
The Meal Recommender System successfully creates tailored meal plans by combining nutritional computations with KNN and TF-IDF techniques. While the recommender meets key nutritional targets, refining the allergy filtering mechanism and enhancing ingredient analysis (e.g., addressing synonyms) are recommended for future iterations.
