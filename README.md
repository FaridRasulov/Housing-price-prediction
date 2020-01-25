# Housing price prediction

## Data Tidying: 

1.Combined the train set and the test set: obtained the data dataset 
2.Remove outliers from TotalBsmtSF,1stFlrSF, GrLivArea,LotFrontage,LotArea,BsmtFinSF1 
3.Eliminate skewness from features which are skewed more than 0.5
4.Scale numeric features with RobustScaler() 

## Missing Data Imputation: 

  1.Categorical Variables: 
    a.Replaced NA values with the mode 
    b.Replaced NA values with “NA” or something similar if the variable refers to a missing categorical attribute of the house. 
    
  2.Numeric Variables: 
    a.Replaced NA with the median value calculated on the observed data (LotFrontage) 
    b.Replaced NA with 0s if the variable refers to a missing attribute of the house  (e.g. GarageYrBlt, MasVnrArea, BsmtHalfBath) 

## Feature Engineering: 
  1.Create new features numYr, numYrRemod, numYrGarage 
  2.Converted ordinal and categorical into numeric ranking (e.g. Alley, BsmtCond, BsmtExposure) 
  3.Converted numeric feature to categorical (MSSubClass) 
  4.Convert some categorical to dummy (Escaping Dummy variables trap) 
  
## Data Visualization : 
  1.Created scatterplots to detect outliers 
  2.Created correlation matrix plot 

## Feature Selection: 
  1.Importance of the features are detected with XGBRegressor 
  2.Finally the features are selected if their importance score is more than 0.005 

## Modelling: 
  1.Our problem is model using Kernel Ridge Regression  
  2.Weighted our result with results coming also from other types of modelling 
    a.Taken our prediction obtained via Kernel Ridge. 
    b.Imported in our environment one result obtained via stacking several models 
    c.Weighted our two different results via harmonic mean.
    
## Submission:        
  1.    Created file for final submission obtaining a score of 0.10858
