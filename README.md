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
a. The loss function is: L(t) = -rt + βt^2
- To find the minimum, we take the derivative of the function with respect to t, set it to zero, and solve for t.
 So, L'(t) = -r + 2βt

-r + 2βt = 0
t= r / 2βt

b. What happens when beta tends to 0 or when it tends to infinity?
- As β→0 (Penalty is weak): The denominator gets very small, so t∗ gets huge. This means the model drifts infinitely far to chase the reward because there is no penalty.
- As β→∞ (Penalty is strong): The denominator gets very large, so t∗ gets close to zero. This means the model refuses to drift at all and stays completely anchored to the reference model.

c. The engineers want t∗≤T no matter what r is.
We know t∗=r/2β. We also know the maximum possible reward is rmax.
The worst-case scenario (maximum drift) happens when r is at its highest (rmax). To ensure the drift never exceeds T, we set the worst-case drift to be equal to T where:
rmax/2β ≤ T
To solve for β:

rmax ≤ 2β*T

β ≥ rmax/2T - This is the proof that by setting β to be at least rmax/2T, you guarantee that even the maximum possible reward won't push the model past the safe limit T.

d. What does this have in common with Problem C?
- In Problem C, the penalty term was λ∑ai^2 .
- In Problem D, the penalty term is βt^2.
- Both terms are Regularization. They both mathematically punish the model for having values that are too large (either large coefficients or a large drift). This forces the model to find a "simpler" or "safer" solution closer to zero, preventing it from overfitting.

## Problem E: Farming Advice
### Opportunities of deploying the system
1. Low Barrier to Entry: Rural farmers do not need to learn complex software. They can type or speak plain Nepali (if the LLM supports it well), asking natural questions like "My rice leaves are yellowing, what should I do?"
2. Instant Triage & Translation: The system can act as a 24/7 first responder, instantly translating complex agricultural science into localized, actionable advice, reducing the wait time to see a human expert.
3. Scalability at Near-Zero Marginal Cost: Once deployed, the system can handle thousands of simultaneous queries from farmers across the region without needing to hire thousands of human agronomists.
### Risks of deploying the system
1. Catastrophic Hallucinations (Crop Destruction): LLMs are designed to sound confident, not to be factually correct. If a farmer follows a hallucinated advice on pesticide dosage, it could destroy an entire season's yield and devastate a family's income.
2. The Infrastructure Failure: Assuming rural Nepal has stable electricity and high-speed internet to ping a US-based cloud server is a massive assumption. The system will be unusable for the most vulnerable populations.
3. Loss of Local Context: Off-the-shelf models don't know the specific local soil conditions, micro-climates or seed varieties. An answer that is statistically true for "general rice" might be completely wrong for a specific demographic.
