# Data_Wranglers_Microplastics_Dataset_Project

## Introduction
Microplastics are a growing concern globally, and pollution from one side of the world will get into the water system and can impact water sources all over the globe. While the health risks of PE (Polyethylene) remains uncertain when consumed, there is the possibility that the plastic particles can absorb and transport harmful chemicals. We are planning to predict the levels of PE in drinking water based on geographic location. We will be using latitude and longitude to measure the locations, size of the microplastic, as well as analyzing trends along country and region borders. Predicting the levels of PE in drinking water is an important step in increasing awareness and supporting change that can reduce these levels in the future.

## Selection of Data
The dataset we decided on is the 'Microplastics in Drinking Water' (specifically the file titled “Microplastics Sample Data (wide)”), which was published by the California State Water Resources Control Board on catalog.data.gov. Each row in this dataset indicates a water sample recorded and columns with information related to that sample. Some of the particular columns that we are interested in are: microplastic materials and types (there is a column for each microplastic type/material and the amount of it present in the sample),colors, tap vs bottled water, and locations where the data was gathered as well as their approximate longitudes and latitudes. Because we are only focusing on the PE (Polyethylene) material, the other “Material” columns will need to be dropped, as they won’t be relevant to our prediction.

The original dataset has more than 100 columns and after some deliberation we decided to drop the ones with less than 40 values right away, but after that we can still see a few missing values that need to be cleaned. Then we drop some unnecesary columns such like 'Sample_ID' and at the same time get rid of all the NAN or 'Present' values for the materials we are looking for, since these entries wouldn't provide us any useful information. We also dropped a section of samples from reservoirs and water storage loctions mainly in China as they have quite inflated values and throw off the models.

Dataset Origin: https://catalog.data.gov/dataset/microplastics-in-drinking-water

Validation Rules (Sample Data): https://data.ca.gov/dataset/e7624fce-c058-4fa1-a29f-2594d8f8f160/resource/2cffd2f1-451f-4253-9050-15c2a9bb298d/download/validation_rules_samples_merged.csv

Microplastics Sample Data (wide): https://data.ca.gov/dataset/e7624fce-c058-4fa1-a29f-2594d8f8f160/resource/b027a5ef-d42e-415c-b9b9-257c1bd5ae89/download/samples_geocoded.csv

## Methods
What materials/APIs/tools were used or who was included in answering the research question?

## Results
What answer was found to the research question; what did the study find?
Was the tested hypothesis true? Any visualizations?

## Discussion
What might the answer imply and why does it matter? 
How does it fit in with what other researchers have found? 
What are the perspectives for future research? 
Survey about the tools investigated for this assignment.

## Summary
Most important findings.
