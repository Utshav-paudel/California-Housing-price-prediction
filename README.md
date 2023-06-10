# California-Housing-price-prediction

### Loading of data and EDA
![calforinaday1](https://github.com/Utshav-paudel/MachineLearning-DeepLearning/blob/24ea2817f4f7092bfa8ff472f0a2b8000dd8183d/images/day39%20Calfornia-dataloading%20and%20Eda.png)
![Eda result](https://github.com/Utshav-paudel/MachineLearning-DeepLearning/blob/5bac9c7462071160bf06432031e4bc21bdf2d304/images/day40%20California%20eda%20resul.png)
### Creating test data 
* Today I Created test data , and splitted data on the basis of train-test-split and also with stratifcation split to remove imbalance in data and create same proportion.   
**Creating test data**
![testdata](https://github.com/Utshav-paudel/MachineLearning-DeepLearning/blob/5bac9c7462071160bf06432031e4bc21bdf2d304/images/day40%20california%20creating%20test%20set.png)
**Creating Training and test data with random sampling and stratification sampling**
![stratification](https://github.com/Utshav-paudel/MachineLearning-DeepLearning/blob/5bac9c7462071160bf06432031e4bc21bdf2d304/images/day40%20traintest%20vs%20strarification%20split.png)
![sampling in train test split](https://github.com/Utshav-paudel/MachineLearning-DeepLearning/blob/9d17986685775af19e615468114ec3f0089fcac4/images/day40%20stratification%20to%20solve%20imbalance%20in%20class.png)
### Visualization with geographical data
* I plotted geographical visual with respect to population density and housing price to gain better understanding of data   
![](https://github.com/Utshav-paudel/MachineLearning-DeepLearning/blob/5955221f5ea3581accba7a4207088bed30cd68c9/images/day41%20california%20visualization%20of%20geographical%20data%20indication%20housing%20price%20and%20popn.png)
# Checking correlation
* Also plotted scatterplot for coefficient of correlation of median_housing price with respect to different features and found out that it has high correlation with median_income but there was some straight line forming in middle of data which need to be filtered before training for better performance.  
![correlation fig](https://github.com/Utshav-paudel/MachineLearning-DeepLearning/blob/5955221f5ea3581accba7a4207088bed30cd68c9/images/day41%20california%20correlation%20of%20median_house_price%20with%20features.png)
Here is code hope you gain some insight from it :   
![visualization](https://github.com/Utshav-paudel/MachineLearning-DeepLearning/blob/5955221f5ea3581accba7a4207088bed30cd68c9/images/day41%20california%20housing%20code.png)
![correlation code](https://github.com/Utshav-paudel/MachineLearning-DeepLearning/blob/06802a4eb2c9cd3d53efbc6443c0ad1133d8852a/images/day41%20california%20checking%20for%20correlation.png)
### Expermenting with attribute combinations 
* I created some new combination of feature like room per house , bedroom ration, population per house and found that room per house has done well then other features, it got some high negative correlation that indicated the less bedroom ratio more the price.
* Also Prepared data for machine learning algorithm by separating the features and target, and perform cleaning of data, replced missing values by filling it with median as it is less destructive.
![code for data cleaning](https://github.com/Utshav-paudel/MachineLearning-DeepLearning/blob/1a4f6b1318fd7e320d8673a0cd35d2e4e16149df/images/day42%20californina%20data%20cleaning.png)
### Use of Simple Imputer
* The benefit of using SimplImputer is that it will store the median value of each feature: this will make it possible to impute missing values not only on the training set, but also on the validation set,the test set, and any new data fed to the model.
![photo of simple imputer use](https://github.com/Utshav-paudel/MachineLearning-DeepLearning/blob/1a4f6b1318fd7e320d8673a0cd35d2e4e16149df/images/day42%20california%20handling%20missing%20using%20Imputer.png)
### Handling of text and categorical data
* Text and categorical data can be handled by using ordinal encoder and One Hot encoding but incase of ordinal encoder it think data nearby data are more similar than far data which is not the case in Oceanproximity so we use onehot encoding.
![handling text and categorical data](https://github.com/Utshav-paudel/MachineLearning-DeepLearning/blob/1a4f6b1318fd7e320d8673a0cd35d2e4e16149df/images/day42%20handling%20text%20and%20categorical%20data.png)
### Feature Scaling
* Feature scaling is one of the most important transformation you need to apply to  your data. Without feautre scaling most model will bias one feature with another. Two ways of feature scaling are : 1.Min-max scaling  2.Standarization.
* `Never use fit() or fit_transform() for anything else than training set.`
![feature scaling image](https://github.com/Utshav-paudel/MachineLearning-DeepLearning/blob/92006ed56d2928f2f3dd6faa3a5121d612bc2657/images/day43%20featurescaling%20california%20code.png)
### Bucketing/Binning
The transformation of numeric features into categorical features, using a set of thresholds, is called bucketing (or binning)
![](https://github.com/Utshav-paudel/MachineLearning-DeepLearning/blob/a57d93feaa03386c050725ae72b64cf9b36a848b/images/day43%20bucketing%20concept.png)
### Column Transformer
* Column transformer is a versatile tool in machine learning that allows for the application of different preprocessing steps to different columns or subsets of columns in a dataset. It simplifies the preprocessing workflow, enhances reproducibility, and improves the efficiency of feature engineering in machine learning tasks.
### Pipeline
* Pipeline refers to a sequence of data processing steps that are applied in a specific order. It combines multiple operations, such as data preprocessing, feature engineering, and model training, into a single cohesive workflow. It make easier to apply same preprocessing to training and test set
![](https://github.com/Utshav-paudel/MachineLearning-DeepLearning/blob/07d1d3751f7f719a5ecdef3583ed8f435332ea30/images/day44%20columntransformer%20and%20pipeline%20california%20housing.png)
### Select and train a model
* I trained some model like LinearRegression, DecisionTreeRegressor and RandomForestRegressor and found out RMSE very high in LinearRegrssion which indicated underfitting and RMSE 0 in DecisionTreeRegressor which was heavily overfitting and RMSE was comparatively low on RandomForestRegressor.So, I  find that RandomForestRegressor can be a good choice
![selecting model](https://github.com/Utshav-paudel/MachineLearning-DeepLearning/blob/640b2d5857962c1dcde47ca02e92316c9f989e5a/images/day45%20california%20selcting%20and%20training%20model.png)
### Evaluation of CrossValidation and Fine tunig the model
* Performing CrossValidation also showed that Random forest was good choice despite of some overfitting and After some tuning in RandomForestRegressor using GridSearch CV I got some good hyperparameter and model perform more better than before and RMSE was also reduced.
![last day code](https://github.com/Utshav-paudel/MachineLearning-DeepLearning/blob/640b2d5857962c1dcde47ca02e92316c9f989e5a/images/day45%20evaluation%20%20of%20cv%20and%20finetuning%20of%20model.png)

