# Evolution_of_Digital_Learning_in_USA_During_COVID19

# Table of Contents

1. [Introduction](#introduction)
2. [Data Preprocessing and Exploration](#data-preprocessing-and-exploration)
3. [Feature Distributions Visualization](#feature-distributions-visualization)
     - [Districts per State](#districts-per-state)
     - [Locale Distribution](#locale-distribution)
     - [Educational Product Providers](#educational-product-providers)
     - [Educational Sector Distributions](#educational-sector-distributions)
     - [Primary Functions with Main and Subcategories](#primary-functions-with-main-and-subcategories)
     - [Essential Function Subcategories Distribution](#essential-function-subcategories-distribution)
     - [Top Educational Products](#top-educational-products)
4. [Distribution of Race, Reduced Fee, Expenditures, and Internet Connection per State](#distribution-of-race-reduced-fee-expenditures-and-internet-connection-per-state)
   - [Black and Hispanic](#black-and-hispanic)
   - [Reduced Fee or Free Education](#reduced-fee-or-free-education)
   - [Per-Pupil Total Expenditure](#per-pupil-total-expenditure)
5. [Time Series Distribution of Educational Product Access for Students](#time-series-distribution-of-educational-product-access-for-students)
   - [Based on Locale](#based-on-locale)
   - [Based on Top Five States](#based-on-top-five-states)
   - [Based on Top Least States](#based-on-top-least-states)
6. [Geographical Analysis](#geographical-analysis)
   - [Education Products Access per State](#education-products-access-per-state)
   - [Engagement Index Per State](#engagement-index-per-state)
7. [Focusing on People from Impoverished Neighborhoods](#focusing-on-people-from-impoverished-neighborhoods)
   - [Black/Hispanic Products Access Over the Year](#blackhispanic-products-access-over-the-year)


## Introduction
There is an imbalance in the education system during the Covid19 pandemic and most of the students don't even have access to educational tools and online learning platforms. There is an urgent need to come up with solutions and by using LearnPlatform dataset I will figure some of the common patterns and identify the clusters based on demography, geography, and accessibility.

## Project Goals
In this project, I will be using data analysis tools to figure out trends in digital learning and how it is effective towards improvised communities. I will be comparing districts and states on factors like demography, internet access, learning product access, and finance. In the end, I will summarize our report and point towards the areas that need our more attention to make education accessible for all students the United States.

Datasets: https://www.kaggle.com/competitions/learnplatform-covid19-impact-on-digital-learning/data

## Data Description

### Data
We have three types of Dataset.
1. Products data contains Sevice names, Companies, and educational sectors.
2. District data contains Demography, Locations, and Educational Spendings.
3. Engagement data contains student's engagement with different products per day.

### Product
The product file `products_info.csv` includes information about the characteristics of the top 372 products with most users in 2020. The categories listed in this file are part of LearnPlatform's product taxonomy.

| **Name**                       | **Description**                                                                                                                                                                                                                                                                                                                    |
|----------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| LP ID                      | The unique identifier of the product                                                                                                                                                                                                                                                                                           |
| URL                        | Web Link to the specific product                                                                                                                                                                                                                                                                                               |
| Product Name               | Name of the specific product                                                                                                                                                                                                                                                                                                   |
| Provider/Company Name      | Name of the product provider                                                                                                                                                                                                                                                                                                   |
| Sector(s)                  | Sector of education where the product is used                                                                                                                                                                                                                                                                                  |
| Primary Essential Function | The basic function of the product. There are two layers of labels here. Products are first labeled as one of these three categories: LC = Learning & Curriculum, CM = Classroom Management, and SDO = School & District Operations. Each of these categories have multiple sub-categories with which the products were labeled |
|                            |   


### District
The district file ```districts_info.csv``` includes information about the **characteristics of school districts**, including data from
- NCES (2018-19),
- FCC (Dec 2018), and
- Edunomics Lab.

| Name                   | Description                                                                                                                                                                                                                                                                              |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| district_id            | The unique identifier of the school district                                                                                                                                                                                                                                             |
| state                  | The state where the district resides in                                                                                                                                                                                                                                                  |
| locale                 | NCES locale classification that categorizes U.S. territory into four types of areas: City, Suburban, Town, and Rural. See Locale Boundaries User's Manual for more information.                                                                                                          |
| pct_black/hispanic     | Percentage of students in the districts identified as Black or Hispanic based on 2018-19 NCES data                                                                                                                                                                                       |
| pct_free/reduced       | Percentage of students in the districts eligible for free or reduced-price lunch based on 2018-19 NCES data                                                                                                                                                                              |
| countyconnectionsratio | ratio (residential fixed high-speed connections over 200 kbps in at least one direction/households) based on the county level data from FCC From 477 (December 2018 version). See FCC data for more information.                                                                         |
| pptotalraw             | Per-pupil total expenditure (sum of local and federal expenditure) from Edunomics Lab's National Education Resource Database on Schools (NERD$) project. The expenditure data are school-by-school, and we use the median value to represent the expenditure of a given school district. |

### Engagement data
The engagement data are aggregated at school district level, and each file in the folder `engagement_data` represents data from **one school district**.


| Name             | Description                                                                                                    |
|------------------|----------------------------------------------------------------------------------------------------------------|
| time             | date in "YYYY-MM-DD"                                                                                           |
| lp_id            | The unique identifier of the product                                                                           |
| pct_access       | Percentage of students in the district have at least one page-load event of a given product and on a given day |
| engagement_index | Total page-load events per one thousand students of a given product and on a given day                         |


## Feature Distributions Visualization
### Districts per states
As we can see the dataset contains more districts from Utah and Illinois than any other state.
<img width="800" alt="image" src="https://github.com/user-attachments/assets/86c9b0e4-ddaa-4568-9525-3c25056868f3">

### Locale Distribution
The suburbs are dominating with 59 percentage, which also means people from medium to high class have more access to internet.
<img width="500" alt="image" src="https://github.com/user-attachments/assets/23b1f332-2c31-4bc6-a080-fc1fc7226eba">

### Educational Product Providers
Google provide most educational products then any one close to it.
>In short online education is dominatied by Google LLC
<img width="800" alt="image" src="https://github.com/user-attachments/assets/75057fa6-d96c-4d4b-8d38-06076ee24bdf">

### Educational Sector Distributions
Educational sectors are divided into three categories, PreK-12, Higher Education, and Corporate.
>Some products are specific to a sector but others are quite general.
<img width="500" alt="image" src="https://github.com/user-attachments/assets/40928a2b-55ad-4383-9ecd-c9e0d0d9ccb4">

### Primary Functions with main and subcategories
There are three types of main primary functions.
1. LC = Learning & Curriculum
2. CM = Classroom Management
3. SDO = School & District Operations.

We can interact with Plotly sunburst plot to explore the distribution of main categories and subcategories.

>The Learning products have majority shares in this group and the most common subcategories are digital learning platforms.
>
><img width="400" alt="image" src="https://github.com/user-attachments/assets/564206b4-dcd2-45b2-863d-6b619b2c33bc">

### Essential Function Subcategories Distribution
We can observe all the subcategories distribution.

> Content creation and digital learning are leading in this market.
<img width="800" alt="image" src="https://github.com/user-attachments/assets/9e664c47-3d1a-43a6-aa3e-13b0406a570f">

### Top Educational Products
Google products are dominating with Wikipedia and Netflix as an exception. Netflix provides kids with educational seise and tutorials.
<img width="800" alt="image" src="https://github.com/user-attachments/assets/ee62a787-c5e3-4d7f-8917-5c46a61e7957">

## Distribution of Race, Reduced Fee, Expenditures, and Internet connection per state
I will be used the Pandas function to display a table showing the mean distribution of various features related to demography and expenditures.

### Black and Hispanic
I seems like Taxes have more Black/Hispanic students than another state followed by Florida, Michigan, and Minnesota.
<img width="200" alt="image" src="https://github.com/user-attachments/assets/0956f6b7-8faa-4867-be10-087b02f1450d">

### Reduced Fee or Free Education
Minnesota provides 70 percent of free or reduced fee education, followed by Michigan and Indiana.
<img width="200" alt="image" src="https://github.com/user-attachments/assets/d473b4bb-adc5-4c3f-8f23-97a0a01fedd7">

### Per-pupil total expenditure
New York spend more on education than any other State in US. The runner-up States are New Jersey and Minnesota.
<img width="200" alt="image" src="https://github.com/user-attachments/assets/14675771-afe8-4646-8cfd-b36f5941f984">

## Time Series Distribution of Educational Product Access Students
I will be observing time-series distributions of Product Access Based on Locale and State.

### Based on Locale
The cities were hit with Covid19 the hardest which affected the students the most as they have to study from home that is why we can see the dip in product access from April to July 2020 as compared to other locales. During Summer vacation students stopped using educational products. In suburbs, students have more access to the tools then other locale. overall, they all follow a common pattern.
<img width="800" alt="image" src="https://github.com/user-attachments/assets/64659e19-1591-40fe-af15-79f5babee4c8">

### Based on Top Five States
New York was hit hardest with Covid19 and that didn't affect the online learning of students as you can see graph became more consistent after the lockdown.
>New York, Wisconsin, and Indian have higher students using these educational products overall.
<img width="800" alt="image" src="https://github.com/user-attachments/assets/fc7c9bf5-7911-47c6-afaf-4bf20dabe75c">

### Based on Bottom Five States
This is odd as Michigan and North Carolina have almost zero product access from March till the end of August. The Texas have a similar pattern but they had a peak in June. Overall these bottom states became active after September 2020.

> It is strange that some states have a very odd pattern, maybe due to a bad educational system or lack of awareness.
> <img width="800" alt="image" src="https://github.com/user-attachments/assets/d8178c97-eccc-41cf-b702-0c3b4e072433">

## Geographical Analysis
In this section I will be looking at different states based on product access and engagement index.
>We do not have access to all states data so you might see a lot of gray space on the map.

### Education Products Access per State
New York has a higher product access score than any other state, then comes Orange States Wisconson, Illinois, and Indiana. There might be a link between the lower population of Black/Hispanics in these states. Let's explore that in the next part.
<img width="500" alt="image" src="https://github.com/user-attachments/assets/f2618c50-36d9-471f-ab47-87188eb36461">

### Engagement Index Per State
The Engagement distribution per state is quite similar to product access. It's logical that if students have access to these products there is a chance of an increase in usage of these platforms.
<img width="500" alt="image" src="https://github.com/user-attachments/assets/5c200a02-ddf8-4d20-a8b4-bcf67b3a45df">

## Focusing on People from Improvised Neighborhood
In this section, I will be focusing on the Black/Hispanic community and free or reduced fees.

### Black/Hispanic products access over the year.
The graph below shows that over time the communities with a lesser population of Blacks and Hispanics have a similar pattern to some of the Top states we have discussed earlier. Let's compare this graph with the mixed communities.

<img width="800" alt="image" src="https://github.com/user-attachments/assets/188ddd90-374e-4e8c-8ba1-fdd2e6052b7b">

We can see some changes as the peak has fallen from 1.4 to 1.2. It is a disparity among the different racial groups but its marginal compares to other countries. We can say Black/Hispanic communities have lesser access to educational products.

<img width="800" alt="image" src="https://github.com/user-attachments/assets/da07aec2-ea3c-4fec-9b99-9a22fd4e6c23">

## Conclusion
The data is limited to fewer states and I didn't found any concrete evidence that Black or Hispanic communities get unfair treatment. Online education is fairly balanced towards all. I did see how some of the states perform worst in terms of product access rating, this might be due to bad policymaking and lack of awareness. We can see that Google is dominating the online education industry by providing a complete ecosystem. The majority of Pre-K students are using these platforms for digital learning. Suburbs have the highest students accessing these products and we can see a clear correlation between product access and engagement index. There is also a high correlation between Black/Hispanic and Free education/ Reduced Fee, which means the government is doing its best to help the poor community by providing free education.

























