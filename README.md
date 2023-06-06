# deep-learning-challenge

# OVERVIEW
The purpose of this analysis is to reflect on the creation and evaluation of the model in the attempt to predict the success of future venture funding. An accurate model may allow for a more efficient use of resources by ALPHABET SOUP.

# RESULTS

## DATA PREPROCESSING

- What variable(s) are the target(s) for your model?
  "IS_SUCCESSFUL" is the target variable for the model.
  
- What variable(s) are the features for your model?
  APPLICATION_TYPE            17
  AFFILIATION                  6
  CLASSIFICATION              71
  USE_CASE                     5
  ORGANIZATION                 4
  STATUS                       2
  INCOME_AMT                   9
  SPECIAL_CONSIDERATIONS       2
  ASK_AMT                   8747
  
- What variable(s) should be removed from the input data because they are neither targets nor features?
  "EIN" and "NAME" were both removed from the input data as they are unique identifiers and are thus neither targets nor features.


## COMPILING, TRAINING, and EVALUATING the MODEL

- How many neurons, layers, and activation functions did you select for your neural network model, and why?
  I initially chose 3 layers with 3-8-1 neurons, respectively. The first and second layers used "Relu" activation and the output layer </br>
  used "Sigmoid" activation as the target variable, "IS_SUCCESSFUL" is binary.
- Were you able to achieve the target model performance?
  Unfortunately I was unable to achieve the target model performance of >75% accuracy, though, with some optimization I was able to achieve </br> a peak accuracy of 73.05% (See [AlphabetSoupCharity_Optimization3.ipynb](https://github.com/zmoloci/deep-learning-challenge/blob/main/AlphabetSoupCharity_Optimization3.ipynb) and [AlphabetSoupCharity_optimization3.h5](https://github.com/zmoloci/deep-learning-challenge/blob/main/AlphabetSoupCharity_optimization3.h5) ).
- What steps did you take in your attempts to increase model performance?
  - First, I increased the layers to 4 layers with 3-8-8-1 neurons, respectively, while maintaining the activation configuration of the </br> three layers as "Relu" and the output activation as "Sigmoid" following the initial logic outlined above. This provided an increase in accuracy from 72.52% (for the initial model's configuration [AlphabetSoupCharity.ipynb](https://github.com/zmoloci/deep-learning-challenge/blob/main/AlphabetSoupCharity.ipynb) and [AlphabetSoupCharity.h5](https://github.com/zmoloci/deep-learning-challenge/blob/main/AlphabetSoupCharity.h5)) to 73.03% (see [AlphabetSoupCharity_Optimization.h5](https://github.com/zmoloci/deep-learning-challenge/blob/main/AlphabetSoupCharity_Optimization.h5)[AlphabetSoupCharity_Optimization.ipynb](https://github.com/zmoloci/deep-learning-challenge/blob/main/AlphabetSoupCharity_Optimization.ipynb)).
  - Next, I increased the neurons per layer to a configuration of 8-32-32-1 with the same configuration of activation types. This did not increase the accuracy of the model at only 72.91% (see [AlphabetSoupCharity_Optimization2.h5](https://github.com/zmoloci/deep-learning-challenge/blob/main/AlphabetSoupCharity_Optimization2.h5)[AlphabetSoupCharity_Optimization2.ipynb](https://github.com/zmoloci/deep-learning-challenge/blob/main/AlphabetSoupCharity_Optimization2.ipynb))
  - Next, I removed two features from the input: "STATUS" and "SPECIAL_CONSIDERATIONS". This resulted in the highest realized accuracy of 73.05% - a marginal improvement over the first optimization. (See [AlphabetSoupCharity_Optimization3.ipynb](https://github.com/zmoloci/deep-learning-challenge/blob/main/AlphabetSoupCharity_Optimization3.ipynb) and [AlphabetSoupCharity_optimization3.h5](https://github.com/zmoloci/deep-learning-challenge/blob/main/AlphabetSoupCharity_optimization3.h5)).
  - Finally, I removed an additional feature: "AFFILIATION". This proved to significantly decrease the accuracy of the model; down to 65.26%. Though this was not the desired result, it effectively shows the importance of this feature to the predictive capability of the model. (See [AlphabetSoupCharity_Optimization3.ipynb](https://github.com/zmoloci/deep-learning-challenge/blob/main/AlphabetSoupCharity_Optimization4.ipynb) and [AlphabetSoupCharity_optimization3.h5](https://github.com/zmoloci/deep-learning-challenge/blob/main/AlphabetSoupCharity_optimization4.h5))
 

# SUMMARY

Although the goal of 75% accuracy was not achieved, much was learned about the dataset and with further resource investment, I am confident that the 75% accuracy benchmark would be achievable.


# DATASET ([charity_data.csv](https://static.bc-edx.com/data/dl-1-2/m21/lms/starter/charity_data.csv))
|index|EIN|NAME|APPLICATION\_TYPE|AFFILIATION|CLASSIFICATION|USE\_CASE|ORGANIZATION|STATUS|INCOME\_AMT|SPECIAL\_CONSIDERATIONS|ASK\_AMT|IS\_SUCCESSFUL|
|---|---|---|---|---|---|---|---|---|---|---|---|---|
|0|10520599|BLUE KNIGHTS MOTORCYCLE CLUB|T10|Independent|C1000|ProductDev|Association|1|0|N|5000|1|
|1|10531628|AMERICAN CHESAPEAKE CLUB CHARITABLE TR|T3|Independent|C2000|Preservation|Co-operative|1|1-9999|N|108590|1|
|2|10547893|ST CLOUD PROFESSIONAL FIREFIGHTERS|T5|CompanySponsored|C3000|ProductDev|Association|1|0|N|5000|0|
|3|10553066|SOUTHSIDE ATHLETIC ASSOCIATION|T3|CompanySponsored|C2000|Preservation|Trust|1|10000-24999|N|6692|1|
|4|10556103|GENETIC RESEARCH INSTITUTE OF THE DESERT|T3|Independent|C1000|Heathcare|Trust|1|100000-499999|N|142590|1|
