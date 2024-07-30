# Social_Capital_and_Economic_Mobility
In this project we will replicate visualizations of two studies carried out on social capital. The studies appeared in the journal Nature:

*  [Chetty, R., Jackson, M.O., Kuchler, T. et al. Social capital I: measurement and associations with economic mobility. Nature 608, 108–121 (2022).](https://doi.org/10.1038/s41586-022-04996-4)

* [Chetty, R., Jackson, M.O., Kuchler, T. et al. Social capital II: determinants of economic connectedness. Nature 608, 122–134 (2022).](https://doi.org/10.1038/s41586-022-04997-3)

First, we will replicate the Figure 2a of the first paper:

<p align="center">
  <img src="https://github.com/user-attachments/assets/7a17f0b1-5e71-486a-aca7-690ba66c2c4e" alt="Figure 2a of the first paper">
</p>

But while the figure in the paper is static, we will create an interactive figure, like the one that is available online at [www.socialcapital.org]( https://www.socialcapital.org/)

The map that we created is constructed using Plotly. The data are displayed per county. When the pointed hovers each county, display the name of the county and the state it belongs to, the code of the county, and the economic connectedness of the county. If there are no data for a particular county, it be painted with a distinct color (in our implementation it is painted gold) and the economic connectedness given as "NA".

For the second visualizations of our project we will replicate Figure 4 of the first paper.
The figure is a scatter plot of upward income mobility against economic connectedness (EC) for the 200 most populous US counties. The income mobility is obtained from the [Opportunity Atlas](https://www.nber.org/papers/w25147), whose replication data can be found [here](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/NKCQM1). Our figure should look like the following one.

<p align="center">
  <img src="https://github.com/user-attachments/assets/213caa8d-5719-4b47-a3e7-31df8b47d1e0" alt="Figure 2a of the first paper">
</p>

For the thrid visualization we will replicate Figure 6 of the first paper:

<p align="center">
  <img src="https://github.com/user-attachments/assets/1676991d-983d-4733-9dea-e68dc24901f6" alt="Figure 2a of the first paper">
</p>

The figure is a scatter plot of economic connectedness (EC) against median household income. We need to compiled data from replication package of the papers with data from the Social Capital Atlas Datasets. The color of the dots corresponds to the child's income rank in adulthood given that the parents' income is in the 25th percentile. The colors correspond to five intervals, which are the quintiles dividing our data. Our figure should look like the following one.

For the forth visualizations we will replicate Figure 5a of the second paper:

<p align="center">
  <img src="https://github.com/user-attachments/assets/f9f1d917-78d5-4a10-af41-96dcdc0d9e12" alt="Figure 2a of the first paper">
</p>

The figure depicts the Socio-Economic Status (SES) of parents against the friending bias of students of low SES, with data from the Social Capital Atlas Datasets. Our figure should look like the following one.

Finally, we will replicate Extended Data Figure 3 of the second paper

<p align="center">
  <img src="https://github.com/user-attachments/assets/98194037-0cbe-4c98-9505-f2bbeda5ad2a" alt="Figure 2a of the first paper">
</p>

The figure depicts friending bias against racial diversity. Racial diversity is defined by the [Herfindahl-Hirschman Index (HHI)](https://en.wikipedia.org/wiki/Herfindahl%E2%80%93Hirschman_index), borrowed from investing. Translated here, it is $1 - \sum_{i}{s_i}^2$, where $s_i$ is the fraction of race/ethnicity $i$ (Black, White, Asian, Hispanic, Native American).

The figure contains two scatter plots with their respective regression lines, one for college data and the other for neighborhood data. Each of the two plots displays binned data (that's why you don't see loads of dots and diamonds). The bins are produced by dividing the $x$-axis into ventiles (i.e., 5 percentile point bins); then we plot the mean of the $y$-axis variable against the appropriate mean of the $x$-axis variable in each ventile. 

The mean of the $x$-axis variable, the HHI index, is the weighted mean of HHI:

* For the college plot, the weights are given by the mean number of students per cohort.

* For the neighborhood plot, the weights are given by the number of children with below-national-median parental household income.

The $y$-axis variable:

* For the college plot, it is the mean of the college friending bias.

* For the neighborhood plot, it is the mean of the neighborhood friending bias.


## Dataset

#### Social Capital Dataset
Data for social capital can be found at the [Social Capital Atlas Datasets](https://data.humdata.org/dataset/social-capital-atlas).

Based on Facebook data, these datasets provide Social Capital measures for counties, ZIP codes, high schools, and colleges in the United States. Meta, Opportunity Insights, and researchers from Harvard, New York University, and Stanford collaborated to create the Social Capital Atlas dataset. To protect privacy while maintaining a high level of statistical reliability, they use methods from the differential privacy literature to add noise to these aggregate statistics.

They construct three measures of social capital:

1. **Connectedness**: The extent to which people with different characteristics are friends with each other. This includes our main economic connectedness measure.
2. **Cohesiveness**: The degree to which friendship networks are clustered into cliques and whether friendships tend to be supported by mutual friends. This includes our clustering and support ratio measures.
3. **Civic Engagement**: Indices of trust or participation in civic organizations. This includes our volunteering rate measure.

#### Oportunity Atlas Dataset
Using anonymised longitudinal data from virtually the entire U.S. population, which can be found [here](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/NKCQM1), the author created a publicly accessible map of children's adult outcomes by Census tract. They estimate children's earnings distributions, imprisonment rates, and other adult outcomes by parental income, race, and gender for each tract. These estimations allow them to trace the origins of outcomes like poverty and imprisonment back to the communities where children grew up. They discover that children's results vary dramatically among surrounding tracts: the standard deviation of mean household income at age 35 for children of parents in the 25th percentile of the income distribution is $5,000 across tracts within counties.

First, they demonstrate that the estimates allow for accurate targeting of measures to promote economic opportunity by identifying specific neighborhoods where certain subgroups of children grow up to have bad results. Neighborhoods matter at the most granular level: based on variables such as poverty rates in a child's local Census tract, characteristics of tracts one mile distant have minimal predictive value for a child's results. Because neighborhood circumstances are typically constant through time, their historical estimates are meaningful predictors of outcomes even for children growing up now.

Second, using data from the Moving to Opportunity experiment and a quasi-experimental study methodology evaluating movers' outcomes, they show that the observational estimates are highly predictive of neighborhoods' causal impacts. Then they identify high-opportunity communities that are affordable to low-income families, so contributing to the development of affordable housing legislation. Our assessments of children's long-term outcomes are only weakly connected with traditional proxies for local economic success, such as employment growth rates, indicating that the conditions that foster higher upward mobility are not always the same as those that foster productive labor markets.

### Folder Structure
There are two subfolders, which are as follows:

1. Datasets: This subfolder includes all the necessary datasets we use in our analysis, except of county_outcomes.csv that can be found in the referenced datasets url due to its size.

2. Images: This subfolder includes all exported plots from our analysis in a .png format for the four last task and for the first task in a .html format. 

3. Source_Code.zip: The source code of our solution is stored as a Jupyter notebook with the name "Source_Code.ipynb" which exists inside Source_Code.zip if you extracted it.
