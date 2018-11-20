# What's In Your Food?

Note: the project files and the PowerPoint Presentation are located in **the src folder** in the same repo.

### Background Information:
* Data from 2009-2010 indicates that over **78 million** U.S. adults and about **12.5** million (16.9%) children and adolescents are obese
* Recent reports project that by 2030, half of all adults (**115 million adults**) in the United States will be obese.
* The annual cost of being overweight is $524 for women and $432 for men; annual costs for being obese are even higher: **$4,879** for women and **$2,646 for men.**

### Data For The Project:
*Open Food Facts* database of food products: https://world.openfoodfacts.org/ which contains information about ingredients, origins, brands, retailers, categories, and nutritional facts.

### Our Goals:
1. Solve a regression problem: can we predict energy content of a product if we only know its ingredients, category, and serving size?
2. Make a classifier: can we correctly identify food categories based on nutritional information and serving size?

### Features:
* 3650 ingredients (made binary)
* Additional features included serving size and food categories

## PART 1. REGRESSION

### How Do We Measure Energy?
Energy is measured in kJ. 1 Calorie = 4.184 kJ.

### Metrics:
* RMSE (Root Mean Square Error)
* MAE (Mean Absolute Error)
* R<sup>2</sup>

### Models:
Models | Training Set RMSE |Test Set RMSE
------------ | ------------- |-------------
Ridge Regression|408.3 kJ |388.21 kJ 
Lasso Regression| 448.62 kJ| 428.78 kJ 
Elastic Net| 405.91 kJ |387.73 kJ 
Random Forest| 334.76 kJ |320.92 kJ
XGBoost Regression| 326.05 kJ |330.70 kJ

### Mean Absolute Error (MAE) and R <sup>2</sup>
Models | MAE |R <sup>2</sup>
------------ | ------------- |-------------
XGBoost| 179.85 kJ |0.8149
Random Forest| 169.22 kJ| 0.8257

### Our Best Results:
* RMSE: 320.92 kJ (76 Calories) per 100 g
* MAE: 169.22 kJ (or 40.4 Calories) per 100 g

Energy content of some common products:
* Nutella – 2255 kJ per (539 Calories) per 100 g
* Mixed-berry granola bar – 1506 kJ (364 Calories) per 100 g
* Iced green tea - 71 kJ (17 Calories) per 100 g

## PART 2. FOOD CLASSIFIER
The database has nine possible food categories (sugar snacks, beverages, dairy, cereal and potatoes, fish meat eggs, composite foods, fruits and vegetables, fat and sauces, salty snacks), however, there are 270624 cases of uncategorized food items. We could use machine learning to classify items based on their nutritional content and serving size. What do we get?

### Models:
Models | Training Set Accuracy |Test Accuracy
------------ | ------------- |-------------
Random Forest| 0.9027| 0.87
XGBoost Classifier| 0.903| 0.84

### Potential Uses of Machine Learning Models:
Machine learning models could be actively used by voice assistants (for interactive Calorie prediction based on ingredients), diet apps (diet optimization, e.g. vegan, Ketogenic, gluten-free etc.), healthy food websites and market places (for food recommendation and automated products categorization). 
