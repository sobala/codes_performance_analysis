# AI Model Confirmation Analytics

This project analyzes how users interact with and confirm outputs from an AI model.  
It focuses on understanding both **model performance** and **user trust behavior** through multiple confirmation metrics.

---

## 📊 Project Overview

The system allows users to attempt up to three different questions, each with multiple attempts (new version of a platform is restricted to only 3 attempts).  
Each attempt can result in a **confirmation (True/False)** by the user depending on whether the user agrees with the classification response received by the AI model.
The project evaluates:
- How often users confirm the model’s answers
- How user behavior differs from model correctness
- Why users sometimes fail to confirm or provide ingenuine inputs

---

## 🎯 Objectives

1. **Measure user confirmation rates** at different levels:
   - **Attempt-level**: % of individual attempts that were confirmed.
   - **Question-level**: % of user–question pairs that were ever confirmed.
   - **User-level**: % of users who confirmed at least one question.

2. **Evaluate model accuracy**, independent of user confirmation:
   - Whether the model’s predicted category matches the correct category.
   - Comparison between `CategoryCorrect` (objective correctness) and `IsUserConfirmed` (user perception).

3. **Analyze non-confirmation reasons**, such as:
   - Model error (`model_wrong`)
   - User confusion (`user_confused`)
   - Ingenuine input (`user_ingenuine`)
   - Old labels or outdated categories (`OldLabel`)

---

## 🧮 Data Structure

Each row in the dataset represents one **attempt** by a user.

| Column | Description |
|--------|--------------|
| `SurveySessionID` | Unique session identifier corresponding to a unique user |
| `QuestionID` | Unique question/task identifier |
| `AttemptID` | Sequential attempt number for that question |
| `IsUserConfirmed` | Whether the user confirmed the response (True/False) |
| `CategoryCorrect` | Whether the model prediction was objectively correct |
| `UserInputCorrect` | Whether the user input was genuine or valid |
| `FailureReason` | Reason for failure if not confirmed |
| `SubclassPresent` | Whether the subclassification was provided |

---


