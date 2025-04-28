# Titanic_eda

# Project Overview

This project performs Exploratory Data Analysis (EDA) on the Titanic dataset to uncover patterns and insights regarding the factors influencing passenger survival. The dataset contains details about passengers such as their age, class, sex, number of siblings/spouses aboard, and more. The goal is to analyze and visualize key features, clean the data, and understand the relationships between the features and survival.

📂 Files in this Repository
1. `titanic_eda.ipynb`

    This Jupyter notebook contains the full EDA process, including:

        Data loading: Importing the Titanic dataset.

        Data cleaning: Handling missing values and data preprocessing.

        Exploratory Data Analysis: Visualizing and analyzing key trends and relationships using:

            Bar plots, histograms, and count plots.

            Heatmaps for correlation analysis.

            Handling categorical and numerical features.

        Statistical Summary: Descriptive statistics and interpretation.

2. `train.csv`

    The training dataset that contains the data on passengers, including features like:

        PassengerId, Pclass, Name, Sex, Age, SibSp, Parch, Fare, Embarked, Survived, and others.

    This data is used to perform the EDA and to analyze survival trends.

3. `test.csv`

    The testing dataset contains similar features to the train.csv dataset, but it does not have the Survived column (which is what we are trying to predict).

    This file is provided to test predictions and perform further analysis after training on the train.csv dataset.

4. `titanic_survival_output.csv`

    This CSV file contains the PassengerId and Survived columns. The output file is generated as part of the analysis, which includes the survival status (1 = survived, 0 = did not survive) for each passenger.

# Summary of Findings:
1. Overview of the Data:

The Titanic dataset consists of the following key columns:

    Survived: Whether the passenger survived (1) or not (0).

    Pclass: The class of the passenger (1st, 2nd, or 3rd class).

    Name: The name of the passenger.

    Sex: Gender of the passenger.

    Age: Age of the passenger.

    SibSp: Number of siblings/spouses aboard.

    Parch: Number of parents/children aboard.

    Ticket: Ticket number.

    Fare: The fare paid by the passenger.

    Cabin: The cabin where the passenger stayed.

    Embarked: The port of embarkation (C = Cherbourg; Q = Queenstown; S = Southampton).

2. Missing Data:

    Age and Cabin columns contain significant missing values.

        Age has a substantial number of missing entries that are often imputed using the mean or median.

        Cabin is largely missing for many rows, suggesting it may not be the most useful feature for predictions, though it could be used to derive other features (like cabin class).

    Embarked has a small number of missing values, often imputed with the most frequent port (S for Southampton).

    Fare does not have missing values after imputation.

3. Univariate Analysis:

    Survived:

        Approximately 38% of passengers survived (Survived = 1), and 62% did not (Survived = 0).

        This indicates a somewhat imbalanced dataset.

    Pclass:

        The majority of passengers were in the 3rd class (around 55%), followed by 1st class (around 25%) and 2nd class (around 20%).

    Sex:

        A higher proportion of females survived (about 74%), compared to males (about 18%).

    Age:

        The age distribution shows a higher concentration of younger passengers (below 30 years).

        There are a few extreme values (outliers), especially for passengers with extremely high ages (above 60).

    SibSp/Parch:

        Many passengers traveled alone, as evidenced by most entries having SibSp and Parch equal to 0.

        Some passengers traveled with family members (parents/children or siblings/spouses), with a few having 5 or more relatives aboard.

    Fare:

        Fare distribution is skewed with a long tail, indicating that a few passengers paid a significantly higher fare, which likely reflects passengers in higher classes or more luxurious cabins.

4. Bivariate Analysis:

    Survived vs Pclass:

        A higher proportion of passengers in 1st class survived (~62%), followed by 2nd class (~47%) and 3rd class (~24%).

        This suggests that class had a strong influence on survival, with 1st class passengers more likely to survive.

    Survived vs Sex:

        Females had a much higher survival rate than males, with approximately 74% of females surviving compared to just 18% of males.

    Survived vs Age:

        Younger passengers (especially children) had a higher survival rate.

        There is a notable difference between age groups, with older passengers less likely to survive.

    Survived vs Embarked:

        Passengers who boarded from Cherbourg (C) had the highest survival rate (~55%), followed by Queenstown (Q) (~40%), and Southampton (S) (~34%).

5. Multivariate Analysis:

    Sex, Pclass, and Survived:

        Females in 1st class had the highest survival rate.

        Males in 3rd class had the lowest survival rate.

        There’s a strong interaction between gender and class regarding survival, with females in all classes having a higher survival rate.

    Fare, Pclass, and Survived:

        Passengers who paid higher fares, especially in the 1st class, were more likely to survive.

    Embarked and Survival:

        The port of embarkation appears to correlate with survival, with Cherbourg having the highest survival rate, although the effect is more significant when combined with the class and sex.

💡Insights:

    Survival Prediction:

        Pclass, Sex, and Age are strong predictors of survival. Gender (female) and class (1st class) had the largest impact on survival.

        Younger passengers, especially children, were more likely to survive.

    Class Disparity:

        There is a noticeable disparity in survival based on class. First-class passengers had a much higher chance of survival than third-class passengers.

    Gender Bias:

        Women were prioritized for lifeboats, as seen by the much higher survival rate for females, especially in higher classes.

    Potential Feature Engineering:

        The Cabin feature could be used to create new columns like Cabin Class (if it contains useful patterns), or Family Size could be derived from combining SibSp and Parch.

📊 Technologies Used

Python

Pandas

NumPy

Matplotlib

Seaborn

Jupyter Notebook


🙋‍♂️ Acknowledgements

Dataset on Kaggle

Thanks to the open-source Python community
