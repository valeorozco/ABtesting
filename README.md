## AB testing: Data analysis

### Objectives: 

1. Determine if the intervention made in group B generated any impact in conversion rates among A/B groups.
    if so:

    1.a. Determine the effect of the intervention in conversion rates (how large/small is the impact)
   
3. Identify relevant variables associated with convension rates.

### Dataset description: 
* User ID: Serves as an identifier for each user.
* Group: Contains both the control group (A) and treatment group (B).
* Page Views: Number of pages the user viewed during their session.
* Time Spent: The total amount of time, in seconds, that the user spent on the site during the session.
* Conversion: Indicates whether a user has completed a desired action (Yes/No).
* Device: Type of device used to access the website.
* Location: The country in UK where the user is based in.

### Methodology:

1. Exploratory data analysis to answer to the question on whether there are differences in conversion rates (opening an email)
   
<img width="480" height="338" alt="image" src="https://github.com/user-attachments/assets/920a5f59-8435-4ba0-972e-779ba44e5052" />

The plot suggests group B (treatment) do generate more conversion rates than group A. To test how the experimental condition, plus other demographical information affects the conversion I decided to run a logistic regression.

2. Run Logistic regression
 <img width="497" height="169" alt="image" src="https://github.com/user-attachments/assets/369cef56-8236-480c-9ee3-2a5af6e1c852" />

As these coefficients suggest, group is the variable more positively associated with conversion. However as the results are the log of the odds, interpretation is blurry and it is better to convert the coefficients to odds ratio or probabilities. 

3. Convert to odd ratios

<img width="577" height="53" alt="image" src="https://github.com/user-attachments/assets/638ab4f7-3aee-4eea-a79e-1e5134e35b26" />

<img width="789" height="390" alt="image" src="https://github.com/user-attachments/assets/29377fc6-d925-4abe-9b7b-859bc2497b2f" />

What the logit suggest is:

A. The variable that most affects the outcome of conversion is being in the intervention group.

B. Participants from the intervention group are 2.86 times more likely than users from the control group to convert. This can be seen as 349/2481 people from the intervention group converted vs only 136/2519 from the control group did.  

C. Those in the intervention group have 14% probability of conversion compared to the control group, where there is only a 5% chance of conversion.

## Interaction terms to evaluate personalization of treatment

Objective:

Now that we know treatment does increase the likelihood of people converting, we want to know in which cases treatment is more succesful.
Is it when people see the prompt in mobile or in web? Are there any differences across locations?

Questions to be solved:
1. What is the probability of people from the treatment group converting when using mobile and device?
   The probability of people from treatment group converting when using mobile is 13% and when using mobile is 14%
3. What is the probability of people from the treatment group converting when they are/and when they are not from Northern Ireland
   The probability of people from treatment group converting when living and *not* living in Northern Irleand using either device is between 13% and 14%.

### This shows that there are no meaningful differences in conversion dependant on device or if they live in northern irland, what is indeed meaningfully affecting conversion rates is whether the person was assigned to control (A) or intervention(B).
