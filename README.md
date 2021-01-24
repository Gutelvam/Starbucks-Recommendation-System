# Starbucks Capstone Challenge

### Summary

1. [Installation](#installation)
2. [Project Motivation](#motivation)
3. [Data Descriptions](#files)
4. [Results](#results)
5. [Licensing and Acknowledgements](#licensing)

## Installation <a name="installation"></a>

There is necessary an Anaconda distribution of Python and Scikit Surprise library, the notebook contain pip command to run on windows, if you work with other OS you must look for those packages.

## Project Motivation<a name="motivation"></a>

There are many problems when sending offers randomly to your customers, so the main idea is to find a way to label the sentiment of offers by customers and after analyzing, create a recommendation mechanism that can send offers that best suit a particular user. Therefore, we want to optimize the way customers interact with offers.
This work is the Capstone Challenge of the Starbucks from  Udacity Data Scientist Nanodegree. We get the dataset from the program that was created in a simulated form, the data has contain the people behavior of purchasing decisions and how those decisions are influenced by promotional offers based on Starbucks real data.

Using This dataset, was need to choose some questions to answer from the data, and in this case i choose to answer 4 questions as following:

- Which genre is more likely to complete an offer?
- Which gender has highest salaries?
- Which kind of offer has more duration?
- How many users has completed offers?


## Data Descriptions <a name="files"></a>

The notebook available here showcases work related to the above questions and the data set is a simplified version of the real Starbucks.

Data Iformation
The datasets that we have and we are going to read, clean, and analyze. Here is the schema and explanation of each variable in the files:

`portfolio.json`

- ***id*** (string) — offer id
- ***offer_type*** (string) — type of offer ie BOGO, discount, informational
- ***difficulty*** (int) — minimum required spend to complete an offer
- ***reward*** (int) — reward given for completing an offer
- ***duration*** (int) — time for offer to be open, in days
- ***channels*** (list of strings)

`profile.json`

- ***age*** (int) — age of the customer
- ***became_member_on*** (int) — date when customer created an app account
- ***gender*** (str) — gender of the customer (note some entries contain ‘O’ for other rather than M or F)
- ***id*** (str) — customer id
- ***income*** (float) — customer’s income

`transcript.json`

- ***event*** (str) — record description (ie transaction, offer received, offer viewed, etc.)
- ***person*** (str) — customer id
- ***time*** (int) — time in hours since start of test. The data begins at time t=0
- ***value*** — (dict of strings) — either an offer id or transaction amount depending on the record


## Results<a name="results"></a>

All the analysis and main results can be found [here](https://medium.com/@gutto.rdj/starbucks-recommending-for-your-wishs-3106040ee3f).

Here we was unable to make more than 3 prediction per user, this means that the data set is very sparse and we dont have so many data with a good amount of offers completed or at least received and viwed, evaluating the Surprise we got an RMSE of 0.7991 for user Similarity when using built-in Cross Validation, but with Grid Search we didn’t but probably can reach better results but its still time consuming.

Of all the models used to create the recommendation system, it was possible to notice that the SVD had the best performance both using cross-validation with the surprise library. Surprise is very interesting for fast projects due to its similarity with the sci-kit learn, easily usable and implementable.

However, it is possible to realize that he has his shortcomings and difficulties, the recommendation returns the most similar users and it is necessary to carry out a further treatment to find the recommendations, another point is that many users had few recommendations this is due to the low amount of rates user or even the lack of records for this user.
## [Licensing and Acknowledgements](#licensing)<a name="results"></a>
[MIT License](https://github.com/git/git-scm.com/blob/master/MIT-LICENSE.txt).

Thanks for Udacity and Starbucks  for give the oportunity to work with these data.
