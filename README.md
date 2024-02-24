# Data_Wranglers_Microplastics_Dataset_Project

### Video Presentation Link
https://youtu.be/gSm9Ki5wKNo

## Introduction
Microplastics are a growing concern globally, and pollution from one side of the world will get into the water system and can impact water sources all over the globe. While the health risks of PE (Polyethylene) remains uncertain when consumed, there is the possibility that the plastic particles can absorb and transport harmful chemicals. We are planning to predict the levels of PE in drinking water based on geographic location. We will be using latitude and longitude to measure the locations, size of the microplastic, as well as analyzing trends along country and region borders. Predicting the levels of PE in drinking water is an important step in increasing awareness and supporting change that can reduce these levels in the future.

## Selection of Data
The dataset we decided on is the 'Microplastics in Drinking Water' (specifically the file titled “Microplastics Sample Data (wide)”), which was published by the California State Water Resources Control Board on catalog.data.gov. Each row in this dataset indicates a water sample recorded and columns with information related to that sample. Some of the particular columns that we are interested in are: microplastic materials and types (there is a column for each microplastic type/material and the amount of it present in the sample),colors, tap vs bottled water, and locations where the data was gathered as well as their approximate longitudes and latitudes. Because we are only focusing on the PE (Polyethylene) material, the other “Material” columns will need to be dropped, as they won’t be relevant to our prediction.

The original dataset has more than 100 columns and after some deliberation we decided to drop the ones with less than 40 values right away, but after that we can still see a few missing values that need to be cleaned. Then we drop some unnecesary columns such like 'Sample_ID' and at the same time get rid of all the NAN or 'Present' values for the materials we are looking for, since these entries wouldn't provide us any useful information. We also dropped a section of samples from reservoirs and water storage loctions mainly in China as they have quite inflated values and throw off the models.

Dataset Origin: https://catalog.data.gov/dataset/microplastics-in-drinking-water

Validation Rules (Sample Data): https://data.ca.gov/dataset/e7624fce-c058-4fa1-a29f-2594d8f8f160/resource/2cffd2f1-451f-4253-9050-15c2a9bb298d/download/validation_rules_samples_merged.csv

Microplastics Sample Data (wide): https://data.ca.gov/dataset/e7624fce-c058-4fa1-a29f-2594d8f8f160/resource/b027a5ef-d42e-415c-b9b9-257c1bd5ae89/download/samples_geocoded.csv

## Methods
We used Random Forest, kNN Regression, and Decision Tree Regression models for our predictions.
### Model 1 - Random Forest Regressor
For our first model, we chose to try and make predictions on Material_PE (Polyethylene) and chose to use the Random Forest Regressor. While the RMSE was relatively low, the plotted data led us to believe that the Random Forest Regressor was unlikely to work for our predictions, even after changing around some of the training and fit variables and estimators.
### Model 2 - K Neighbors Regressor
For our second model we chose to try the kNN regression model. Overall, the kNN model performance varied with different values of k, but none of the models achieved particularly good performance, as indicated by the relatively high RMSE values. Further experimentation with different algorithms or parameter tuning may be warranted to improve the model's predictive accuracy.
### Model 3 - Decision Tree Regressor
For the last model we tried to do a Decision Tree Regression model. In this case, the relatively low MSE and RMSE values suggest that the decision tree model performed reasonably well in capturing the underlying patterns in the data and making predictions. However, the simplicity and small amount of data make these predictions less valuable.

## Results
Each model was trained and tested using the same dataset, with their respective metrics assessed for accuracy. The Random Forest model yielded a mean squared error (MSE) of 0.017 and a root mean squared error (RMSE) of 0.132. For kNN Regression, varying values of k were explored, resulting in different training and testing RMSEs across different k values, but ultimately had too high of a MSE and RMSE to be used accurately. Finally, the Decision Tree Regression model produced an MSE of 0.013. Overall, these results tell us that the Decision Tree Regression model was the best fit for our dataset, but still was unable to provide a useful prediction for the amount of data we had to work with.

## Discussion
In the end we were unable to provide any reliable predictions based on the values obtained from the dataset. When first selecting the dataset it seemed very promising but later we discovered just how many actual samples we were able to use. Many of the samples had many null values or values with mismatched data types. This made it very difficult to use the majority of the data present at the beginning and after cleaning we only had around 60 samples, most of which fell under the same 7 or so concentration values, making predictions unlikely to be accurate. There are still other models that we could try but at this point the dataset seems to be holding us back the most.

## Summary
This project started out with the goal of reliably predicting the safety of water for consumption based on the amount of microplastics found in similar sources. Once we got into the data we changed predictors to one with a more reliable set of values in the dataset. After compiling and modifying our models we were unable to determine or predict the safety of water as the dataset had a few issues as previously mentioned. This dataset is a work in progress and has been steadily updated since July 21 2022, but until the data becomes more reliable and regulated, there won’t be a way to accurately predict the safety of drinking water based on the microplastics found in similar sources.
