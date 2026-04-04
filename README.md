# Hughes_MS285_Project


## Seasonal Differences in Harbor Seal Diet

**Motivation**

Scientific Research Question: Do the diet proportions of harbor seals differ between seasons (spring; fall)? 

It is important to understand the seasonal variability in harbor seal diets to reveal more about their foraging plasticity and adaptability. Central place foraging theory suggests that harbor seals prefer to forage near their haul-outs due to their moderate to high site fidelity, which in turn encourages a generalist diet (i.e., a more flexible diet), since there is less opportunity to be highly selective when hunting for prey. As prey abundance and composition change from one season to the next, harbor seal diets will change accordingly. Therefore, understanding the seasonal changes in diet composition will allude to the changes in the habitats that make up harbor seals’ local foraging ranges. 

**Data** 

This dataset comes from a [public dataset available on Dryad](https://datadryad.org/dataset/doi:10.5061/dryad.g23j32s) that was published in association with the following article: 

Schwarz, D., Spitzer, S. M., Thomas, A. C., Kohnert, C. M., Keates, T. R., & Acevedo‐Gutiérrez, A. (2018). Large‐scale molecular diet analysis in a generalist marine mammal reveals male preference for prey of conservation concern. Ecology and Evolution, 8(19), 9889-9905. https://doi.org/10.1002/ece3.4474
 
The researchers took scat samples from harbor seal colonies to analyze the diet composition and recorded the sex of the individual, the sample ID, the month, season, and year the sample was collected, the site (i.e., the colony) that the sample was collected from, and the diet proportions by prey species, and diet proportions by prey order.

The original dataset is a .csv file that is posted on Dryad is 160.10 KB. However, I cleaned up the original dataset and created a new .csv file that is 125 KB using Google Spreadsheets, in which I removed the columns with diet proportions by prey order since I just want to focus on diet proportions by prey species: [Link to the data](https://docs.google.com/spreadsheets/d/11cyY0J7lKJY5X8eAhHKByFLa_lifs9Ff2XsDzJniXVM/edit?usp=sharing)


**Model** 

I want to use the diet proportions to determine what season that sample was collected in (spring, summer, winter, or fall) and so, my prediction, or output of the model, will be a season. Most problems are non-linear, so it is safer to make the assumption that my data are non-linear and start by using a KNN classifier. I will normalize the input features so that one parameter does not bias the results. I will include the following features which have been shown to account for variance in the literature: diet composition, with each of the observed prey species in the diet study considered to be one feature; site (with values of Comox and Conwichan Bay); and sex (with values of Female and Male). Finally, I will use the Mean Square Error (MSE) loss function which is a way of measuring the number of observations the model misclassified.


**Analysis** 

I will evaluate my model results by creating a ‘confusion matrix’ that will provide a visualization of the true positives, true negatives, false positives, and false negatives. The confusion matrix will tell me which classes the model confuses the most. An accurate model demonstrates the ability to predict seasonal changes in the diet of harbor seals which will provide insight into how their habitats and prey availability are changing between seasons.

