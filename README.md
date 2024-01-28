# 🏆 Model Overview 🏆

This **Random Forest Classifier** predicts whether an English Premier League team will win a given match. The model incorporates both traditional match factors and rolling performance metrics, providing a nuanced approach to match prediction.

## 🌐 Data

The data used for training and testing this model was web-scraped from https://fbref.com/en/comps/9/Premier-League-Stats. [My Web Scraping Process](EPL_Pred_Scraping.ipynb)

## 🛠 Key Features

1. 🏟 **Venue (Home/Away):** The model considers the significant impact of the match venue by differentiating between home and away games, acknowledging the well-documented home advantage in sports.
2. 🤼 **Opposing Team:** Through numerical encoding, the model accounts for the strength and historical performance of the opposing team, recognizing that some opponents present a tougher challenge than others.
3. ⏰ **Time Factors (Hour and Day of Week):** The model includes the hour of the day and the day of the week of the match, acknowledging potential influences of these temporal factors on team performance, such as player fatigue or audience size.
4. 📊 **Rolling Performance Metrics Based on Last Three Matches:**
   - 🥅 *Goals For and Against:* These metrics provide insight into the team's offensive and defensive capabilities over recent games.
   - ⚽ *Shots Taken and Shots on Target:* These indicate the team's attacking intensity and accuracy.
   - 📏 *Shot Distance:* This offers a perspective on the team’s attacking style, whether they rely on long-range efforts or closer, more precise attacks.
   - 🎯 *Free Kicks, Penalty Kicks, and Penalty Attempts:* These elements add depth to the model by including set-piece proficiency, which can be crucial in tight matches.

## ⚙️ Model Mechanics

The **Random Forest** algorithm aggregates decisions from numerous decision trees, each trained on a subset of the data and features. This approach reduces overfitting and increases the robustness of the model. Each tree contributes to the final prediction, with the aggregate decision (majority vote) determining the predicted outcome of the match.
  -  Training set: All EPL matches from 2020-01-01 to 2023-12-31
  -  Testing set: All EPL matches in 2024 as of 2024-01-25
 


## Model Strengths

- 🛡 **Resilience to Overfitting:** By using multiple trees and subsets of features, the model is less likely to overfit to the training data, making it more generalizable to new, unseen matches.
- 🔄 **Incorporation of Contextual Data:** The use of rolling averages to factor in recent team performance gives the model a dynamic edge, adapting to current forms rather than relying solely on static, season-long data.

## 📈 Applications

This model is particularly useful for sports analysts, betting enthusiasts, and football fans interested in gaining an insightful perspective on upcoming matches. Its predictions can inform pre-match analyses, betting strategies, or even fan discussions.

## 📊 Feature Importance Plot

![image](https://github.com/ammaarmelethil/Premier_League_Match_Winners_Prediction/assets/100314064/44d06bf5-8b9a-43bd-abfa-fd5e52b6ee94)

**Feature Importance Ranking:**
1. Shots taken (Rolling average over last 3 games)
2. Opposing team
3. Distance of shot from goal (Rolling average over last 3 games)
4. Shots on target (Rolling average over last 3 games)
5. Goals against (Rolling average over last 3 games)
6. Goals for (Rolling average over last 3 games)
7. Hour of day
8. Venue (Home/Away)
9. Free kicks (Rolling average over last 3 games)
10. Day of week
11. Penalty kick attempts (Rolling average over last 3 games)
12. Penalty kicks (Rolling average over last 3 games)

