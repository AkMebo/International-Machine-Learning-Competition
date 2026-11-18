# International Machine Learning Competition
## Problem A: Machine Learning Lifecycle (5 points)
A sound-recognition system is developed through the six steps shown below
### Data Collection
1. Collect 10,000 recordings labelled speech, music, or alarm.
### Training
2. Adjust the model’s parameters using these recordings.
### Evaluation
3. Test the model on recordings it has not seen before.
### Deployment
4. Install the model in a school.
### Inference & Deployment
5. The installed model receives a new sound and predicts alarm.
### Training
6. At the end of the month, newly recorded sounds are labelled and used to adjust the model again.

### Step where the system is actually learning
The system is only actually learning during Step 2 and Step 6
- What learning means: Learning occurs specifically when the model's internal parameters are adjusted using data.
- Step 2: The model is actively learning because it is adjusting its parameters.
- Step 6: The model is actively learning again because it is being re-trained on the new data.
- In Steps 1, 3, 4, and 5, the model's parameters are frozen (locked). It is just collecting data, doing math to see how accurate it is, or making predictions. It is not changing or learning during those steps

## Problem B: The Greenhouse Tree (5 points)
#### a) KEEP CLOSED
#### b) 
1. **Is temperature above 28°C?**
    * **Yes** → OPEN the roof
    * **No** → Go to step 2

2. **Is humidity above 70%?**
    * **Yes** → OPEN the roof
    * **No** → Go to step 3

3. **Is CO2 above 1200 ppm?**
    * **Yes** → OPEN the roof
    * **No** → KEEP CLOSED
## Problem C: To Fit or Not to Fit (5 points)
### a) Model 1: J1 = 9.26, Model 2: J2 = 4.08. The scoring model selects Model 2 since 4.08 < 9.26
### b) Model 1 fits the training data perfectly. Its sum of squared errors is exactly 0
   - Model 2 is selected because J is not looking for a perfect fit, it's looking for a balance between fit and simplicity (regularization). Model 1 has high coefficients which are penalized heavily. Model 2 has a smaller error overall when you add the penalty because its coefficients are much smaller and simpler.
   - The term λ∑a^2 is to prevent overfitting. It is a Regularization Penalty. It ensures the model doesn't just memorize the training data (like Model 1 did) but learns a smoother, more general pattern that will hopefully perform better on new, unseen data.

## Problem D: The Price of Drift
## Problem C:  To Fit or Not to Fit (5 points)

