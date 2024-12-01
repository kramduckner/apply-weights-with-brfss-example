# How to work with BRFSS data - Applying weights

I was working with CDC's BRFSS dataset and found their instructions on how to apply weights to be confusing. I also couldn't find any up-to-date python examples, so I decided to create an example
jupyter notebook in case someone might find it useful. You can execute the notebook in [colab](https://colab.research.google.com/), [jupyter lab or jupyter notebook](https://jupyter.org/install), or github's [codespaces](https://github.com/features/codespaces). 
This notebook shows how to map the numerical AGEG5YR_ field to its string value, and apply the LLCPWT weight to it to get a more accurate value.

## What is BRFSS
The CDC's Behavioral Risk Factor Surveillance System (BRFSS) is the largest ongoing health-related telephone survey system in the world. It was established in 1984 by the Centers for Disease Control and Prevention (CDC) to collect data on health-related risk behaviors, chronic health conditions, 
and the use of preventive services among U.S. residents.

## What is a weight?
Weights in the Behavioral Risk Factor Surveillance System (BRFSS) data are crucial for ensuring that the survey results are representative of the population. Since the BRFSS collects data through random sampling of adults in the U.S. (via landline and mobile phone surveys), weighting adjusts for biases and makes the data reflect the actual population demographics and distribution. For example, they use landlines to conduct the questionnaires, so the population that uses landlines don't tend be 100% representative of the entire population, and certain demographic fields like age will over-represent one value. Weights can be applied to adjust these values so they are more representative of the entire population.

## Obtaining the Data
I've included a csv file of the first [100 rows of 2023 brfss data](https://github.com/kramduckner/apply-weights-with-brfss-example/blob/main/first_100_rows_brfss_2023.csv), but you can also go to [CDC's website](https://www.cdc.gov/brfss/annual_data/annual_2023.html) to download the entire dataset.
They only have it available in XPT or ASCII formats, so this notebook also converts the XPT file to csv so Pandas can convert it to a dataframe.

