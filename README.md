# Modelling_BMI
Code for comparing methods to model BMI data from NCD-RisC

## Program Overview

The NCD-RisC BMI data (https://www.ncdrisc.org/index.html) must first be cleaned (NCDRisC_datacleaning.Rmd). Then, we fit frequentist models (Frequentistmodels.Rmd) and Bayesian models (Bayesianmodel_Normal.stan, Bayesianmodel_HALFnormals.stan, Bayesianmodels.Rmd). To combine the frequentist and Bayesian results for the plots presented in the manuscript use: Figures_frequentistbayesiancombined.Rmd. 

To use these programs, the user will need to update filepaths to where they have stored the NCD-RisC data and where they wish for the data and figures to be outputted.

| Program Name | Type of Program | Description |
|--------------|-----------------|-------------|
| NCDRisC_datacleaning.Rmd    | R Markdown | Data cleaning of NCD-RisC BMI data - adds world region to each country and combines male and female data. |
| Frequentistmodels.Rmd     | R Markdown | Simulates synthetic data from the CLEANED prevalence NCD-RisC BMI data and estimates parameters for each age-sex-country group from the frequentist models. Outputs Mean Absolute Differences and Mean Squared Differences (Table 1). Presents heatmaps and calibration plots for 3 frequentist models (Suppl Table 1). |
| Bayesianmodel_Normal.stan     | Stan file | Bayesian multinomial model with NORMAL distribution. |
| Bayesianmodel_HALFnormals.stan     | Stan file | Bayesian multinomial model with SPLIT/HALF-NORMAL distribution. |
| Bayesianmodels.Rmd     | R Markdown | Fits Bayesian models (using Stan files above) to each age-sex-country group and estimates parameters for each. Outputs Mean Absolute Differences and Mean Squared Differences (Table 1). Presents heatmaps and calibration plots for 2 Bayesian models (Suppl Table 1). |
| Figures_frequentistbayesiancombined.Rmd     | R Markdown | Combines the frequentist and Bayesian results into figures that are presented in the manuscript (heatmaps and calibration plot). |
