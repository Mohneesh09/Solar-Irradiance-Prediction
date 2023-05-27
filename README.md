# solar-irradiance-prediction
**Task:** optimize solar power production by building a model which accurately predicts irradiance using some data.
# Problem It Solves
* After witnessing harmful effect of fossil fuels on our enviornment and realising it's exhaustability we are trying to make advancement in renewble clean energy sources.Solar energy energy being one of them is harnessed using solar plates whose orientation along with weather conditions determine how much electricity will be generated.
* This challenge attempts to predict solar irradiance components which will help solar power generation company in maximizing it's electricity generation through proper solar panel orientation.With this we step towards cleaner,non exhaustible energy sources.

 # Challenges along the way
During the course of the project,a few challenges were faced.Some of the challenges and used methods to tackle them are listed below:-
* **Correlated targets :** 
  * First challenge was to figure out way to do multitarget prediction as we had to predict DNI irradiance, DHI irradiance and GHI irradiance all while them being affecting each other.So naive method of handling it was just to predict them separately usng rest of data i n trainig but this had poor performance.Then I came up with a very effective method in which one predicted target was included in train data of other target.
  * This idea was based on imputation techniques in which we first impute missing data points and predict target only after that.
  * Using non target attributes in training, Clearsky DHI was predicted.Then Using non-target+DHI as train data ,GHI was trained ,then using all rest DNI was trained.After all this we have poorly predicted data of all targets.Then DHI was trained using non-targets+GHI+DNI and similarly for others.
  * Above steps were recursively applied few times.This technique effectively used correlation among targets to predict each other.
  * This way a number of models with it's train data schema not necessarily same as others was built
* One hideous challenge along the way was modularizing training and predicting pipeline.Doing this was crucial to train on so many different train data variants corresponding to each target. 
* Hyperparameter optimization: Xgboost being the sota for tabular data had responsibilty to perform well on the data.So I finetuned all it's parameters using *Optuna*.
* **Stacking:**
  Different models were used to ensure that one model does not ovefit.Models used were Xgboost,Linear Regression and Random         forest.Individual models were trained on differnet traindata variants.So all these models were merged using a linearRegression metamodel which does the final prediction.

### TechStacks
Python,Machine Learning, NumPy, Pandas, Sklearn, Optuna
