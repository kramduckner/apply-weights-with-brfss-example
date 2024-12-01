# How to work with BRFSS data - Applying weights

I was working with CDC's BRFSS dataset and found their instructions on how to apply weights to be confusing. I also couldn't find any up-to-date python examples, so I decided to create an example
jupyter notebook in case someone might find it useful. You can execute the notebook in [colab](https://colab.research.google.com/), [jupyter lab or jupyter notebook](https://jupyter.org/install), or github's [codespaces](https://github.com/features/codespaces). 
This notebook shows how to map the numerical AGEG5YR_ field to its string value, and apply the LLCPWT weight to it to get a more accurate value.

## What is BRFSS
The CDC's Behavioral Risk Factor Surveillance System (BRFSS) is the largest ongoing health-related telephone survey system in the world. It was established in 1984 by the Centers for Disease Control and Prevention (CDC) to collect data on health-related risk behaviors, chronic health conditions, 
and the use of preventive services among U.S. residents.

## Obtaining the Data
I've included a csv file of the first [100 rows of 2023 brfss data](), but you can also go to [CDC's website](https://www.cdc.gov/brfss/annual_data/annual_2023.html) to download the entire dataset.
They only have it available in XPT or ASCII formats, so this notebook also converts the XPT file to csv so Pandas can convert it to a dataframe.

