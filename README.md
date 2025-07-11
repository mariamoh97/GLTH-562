# EXECUTIVE SUMMARY

# Research Question

Which factors affect asylum decisions for refugees? More specifically,
which factors enable acceptance of asylum applications?

# Data

**UNHCR R Package: Refugees**

Datasets used:

1.  Population:

    Contains data on forcibly displaced and stateless persons by year,
    including refugees, asylum-seekers, internally displaced people
    (IDPs), and stateless people. It is structured by year, country of
    asylum, and country of origin with separate columns for each
    population group.

2.  Asylum Decisions:

    Provides information on decisions taken on asylum claims by year and
    countries of asylum and origin. It includes data on application
    recognition, rejection, and administrative closures of asylum
    claims.

3.  Asylum Applications:

    Consists of data on asylum applications, detailing the procedure
    type and application type. It helps in understanding the number and
    nature of asylum applications filed over time.

4.  Demographics

    Offers demographic and sub-national data, where available, including
    disaggregation by age and sex. This dataset is vital for
    understanding the demographic profile of displaced population.

**Standalone Dataset for Coordinates**

The dataset named,
*world_country_and_usa_states_latitude_and_longitude_values* was
downloaded from
[Kaggle](https://www.kaggle.com/datasets/paultimothymooney/latitude-and-longitude-for-every-country-and-state?resource=download)

It gives the latitude and longitude values for each country.

# Methodology

**Exploratory Data Analysis and Visualization** The first step was to
understand the data itself before applying any further methods. We
looked at different datasets to understand the most important factors
counted in the refugee applications.

1.  Countries with Highest Refugee Population We wanted to first look at
    what the migration trends look like, specifically some countries of
    interest in the last year of data.

2.  Refugee Types over Decades The next was to then look at historical
    data which could show who are the most frequent types of refugees or
    displaced individuals.

3.  Refugees Settled in Different Regions Based on UNHCR’s regions, we
    try to explore where refugees have settled the most over the years
    to understand how important countries of application can be.

4.  Refugees by Country of Origin In the last decade, we wanted to
    understand where refugees are coming from the most. It gives us a
    better idea of where applications could be coming the most from.

5.  Application Types There were 3 main types of applications- joint,
    UNHCR, and the national government of the country of application.

6.  Application Countries Finally, we move from regions to specific
    countries and chart how preferences have changed over the years when
    applicants apply for asylum. This could give us an idea of which
    countries could be friendlier or deemed safer for those escaping
    violence.

**Prediction Model** In order to assess the rate of application
acceptance, we created a machine learning based prediction model. The
model used was a Random Forest regression model. We used this particular
model since our input variables were categorical in nature while our
output was a continuous value. Tree based models are more amenable to
categorical input without extensive encoding.

Our variable of interest was the acceptance rate of decisions for every
origin-application country pair each year. The value was calculated
using accepted number of applications and the total decisions given by a
particular pair of countries.

The random forest model gave an RMSE value of 0.283 which shows that the
differences between actual and predicted values were small.

Dependent Variable: Acceptance Rate Independent Variables: ISO Codes for
Countries of Origin and Asylum, Procedure Type, Decision Level,
Applicant Type

# Findings

**Exploratory Data Analysis**

1.  Countries with Highest Refugee Population- We see that Syria had the
    largest proportion of refugees in 2022.

![Top 10 Countries of Origin in 2022](data/refugee_countries_top10.jpg)

2.  Europe had the most number of refugees settled

![Regions where Refugees have Settled](data/heatmap.jpg) 3. Most
internally displaced persons belong to African countries and may not
necessarily be looking at asylum applications

![Top 10 Countries of Origin for Internally Displaced Persons from
2012-2022](data/country_of_origin_idpjpg.jpg) **Prediction Model**

4.  The given dataset can help in training a robust model which can
    predict one’s chances of asylum acceptance, given their country of
    origin, where they are applying, who they are submitting the
    application to, and whether they are applying individually or as a
    case group. However, a robust model requires more explanatory data
    and more data cleaning than was done for our base model. At the same
    time, this model can be used as a foundation to improve upon and
    build a stronger predictor analysis.

![Ideal Parameters for Random Forest Model with
Tuning](data/model_parameters.png)

*NOTE*- The folder, **Dashboard_files** contains the main
**dashboard.qmd** file that is our main deliverable.
