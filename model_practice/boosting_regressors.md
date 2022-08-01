## Boosting Regressors

Here we will use boosting to solve a regression problem. Specifically we would
like to predict California house prices based on 8 features.

<br>

Follow these steps to set up the repository on your local machine:

1. Clone the repository if you haven't done so before
   ` git clone git@github.com:ValkyrieIntelligence/vlk-associate-tutorials`

   If you have pulled the repo, pull in the changes from the main branch
   `git pull origin` 

2. From the project folder checkout your own branch
   `git checkout -b [name]`

3. Create a new conda environment
   `conda env update -f model_practice/environment.yml`

4. Activate the enviroment
   `conda activate model_practice`

5. Activate nbstripout
   `nbstripout --install --attributes .gitattributes`

6. Make a copy of the notebook_templete and rename it with your initials 

7. Follow the steps in the notebook to compare 3 classes of ML algorithms. 
   Each group will test one model and report their evaluation metrics at the end. 
   - `RandomForestRegressor` 
      https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html

   - `GradientBoostingRegressor`
      https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.GradientBoostingRegressor.html?highlight=gradient%20boosting#sklearn.ensemble.GradientBoostingRegressor
      
   - `AdaBoostRegressor`
      https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.AdaBoostRegressor.html?highlight=adaboost#sklearn.ensemble.AdaBoostRegressor

   Boosted decision trees (`AdaBoost`, `GradientBoosting` & others)
   have been shown empirically to outperform `RandomForest` on average
   ([_Table 4 - R. Caruana et. al._](./readings/compare_ml_algo.pdf)) in terms
   of predictive power. The runtime for boosting algorithms, as you will
   experience, is also competitive with random forest.

   As a starting point, there are instantiations of the 3 classes of
   algorithms with predetermined hyperparameters. Don't worry about those for now, 
   each group will get to tune their parameters. 

   **Note:**
   `n_jobs=-1` _allows the process to be run on multiple cores on
   your computer. Only parallel algorithms such as_ `RandomForest` _can
   do that. Boosting is sequential (the current step depends on the residuals
   from the previous) and does not have that option._
   `n_jobs=-1` _is not a hyperparameter._


8. Review the MSE and R2 score for all three models based on the current set of 
   hyperparameters.  Which of the models cross validates the best? Why is it 
   inappropriate to make a judgement on the performance of the models based only 
   on the evidence we have thus far?

9. We aim to search for the set of hyperparameters that
    would give us the lowest cross-validated train error. The search of these
    hyperparameters is known as grid-search. For each hyperparameter, a set
    of values are specified. The combination of the hyperparameters at different
    values will constitute the search space. We try each possible combination
    of parameters and find the combination which minimizes error.

    Use `GridSearchCV` for to find the best `RandomForestRegressor`
    and `GradientBoostRegressor` models respectively.
    Remember to specify `n_jobs=-1` in `GridSearchCV` to use all the cores of your
    machine and speed up your search.
