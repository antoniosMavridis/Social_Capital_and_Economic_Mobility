# Social_Capital_and_Economic_Mobility
In this project we will replicate partly visualizations of two studies carried out on social capital. The studies appeared in the journal Nature:

*  [Chetty, R., Jackson, M.O., Kuchler, T. et al. Social capital I: measurement and associations with economic mobility. Nature 608, 108–121 (2022).](https://doi.org/10.1038/s41586-022-04996-4)

* [Chetty, R., Jackson, M.O., Kuchler, T. et al. Social capital II: determinants of economic connectedness. Nature 608, 122–134 (2022).](https://doi.org/10.1038/s41586-022-04997-3)

First, we will replicate [Figure 2a of the first paper](https://www.nature.com/articles/s41586-022-04996-4/figures/2).
<img src=".\Markdown\Fig2a.png" alt="The geography of social capital in the United States." style="width: 50%"/>
But while the figure in the paper is static, we will create an interactive figure, like the one that is available online at https://www.socialcapital.org/.

The map that we created is constructed using Plotly. The data are displayed per county. When the pointed hovers each county, display the name of the county and the state it belongs to, the code of the county, and the economic connectedness of the county. If there are no data for a particular county, it be painted with a distinct color (in our implementation it is painted gold) and the economic connectedness given as "NA".

## Dataset

Data for social capital can be found at the [Social Capital Atlas Datasets](https://data.humdata.org/dataset/social-capital-atlas).

Based on Facebook data, these datasets provide Social Capital measures for counties, ZIP codes, high schools, and colleges in the United States. Meta, Opportunity Insights, and researchers from Harvard, New York University, and Stanford collaborated to create the Social Capital Atlas dataset. To protect privacy while maintaining a high level of statistical reliability, they use methods from the differential privacy literature to add noise to these aggregate statistics.

They construct three measures of social capital:

1. **Connectedness**: The extent to which people with different characteristics are friends with each other. This includes our main economic connectedness measure.
2. **Cohesiveness**: The degree to which friendship networks are clustered into cliques and whether friendships tend to be supported by mutual friends. This includes our clustering and support ratio measures.
3. **Civic Engagement**: Indices of trust or participation in civic organizations. This includes our volunteering rate measure.
