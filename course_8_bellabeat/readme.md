# How Can a Wellness Technology Company Play It Smart?

- This case case study explores 

- Scenario details for the case study can be found in the [Appendix](#appendix)

## Table of Contents

- [Introduction](#introduction)
- [Business Objective](#business-objective)
- [Preparation of the Data](#preparation-of-the-data)
- [Processing the Data](#processing-the-data)
- [Analyzing the Data](#analyzing-the-data)
- [Visualizations](#visualizations)
- [Deliverables](#deliverables)
- Appendix
  - [Appendix - Code](#appendix---code)
  - [Appendix - Scenario](#appendix---scenario)


## Introduction

Bellabeat is a tech company that manufactures health products for women and wants to increase growth in the smart device market. The cofounders utilised one of their backgrounds as an artist to develop beautifully designed technology that informs and inspires women around the world.

The company has invested in traditional advertising media, such as radio, out-of-home billboards, print, and television, but focuses on digital marketing extensively. Bellabeat invests year-round in Google Search, maintaining active Facebook and Instagram pages, and consistently engages consumers on Twitter. Additionally, Bellabeat runs video ads on Youtube and display ads on the Google Display Network to support campaigns around key marketing dates.

The Bellabeat app provides users with health data related to their activity, sleep, stress, menstrual cycle, and mindfulness habits. This data can help users better understand their current habits and make healthy decisions. The Bellabeat app connects to their line of smart wellness products:
- **Leaf**: Bellabeat’s classic wellness tracker can be worn as a bracelet, necklace, or clip. The Leaf tracker connects to the Bellabeat app to track activity, sleep, and stress.
- **Time**: This wellness watch combines the timeless look of a classic timepiece with smart technology to track user activity, sleep, and stress. The Time watch connects to the Bellabeat app to provide you with insights into your daily wellness.
- **Spring**: This is a water bottle that tracks daily water intake using smart technology to ensure that you are appropriately hydrated throughout the day. The Spring bottle connects to the Bellabeat app to track your hydration levels.

Bellabeat also offers a subscription-based membership program for users. Membership gives users 24/7 access to fully personalized guidance on nutrition, activity, sleep, health and beauty, and mindfulness based on their lifestyle and goals.

The CCO believes that analyzing consumer data for the usage of non-Bellabeat smart devices will provide the insight needed to guide future marketing strategies for their own products


## Business Task

Analyse trends in non-Bellabeat smart device usage and provide insight to inform the marketing strategies for one Bellabeat product and unlock new growth opportunities.

Key stakeholders:
- Urška Sršen: Bellabeat’s cofounder and Chief Creative Officer
- Sando Mur: Bellabeat’s cofounder
- Bellabeat marketing analytics team

## Preparation of the Data

The [FitBit Fitness Tracker Data](https://www.kaggle.com/datasets/arashnic/fitbit) set from Kaggle was used:
- Accopmanying journal article available through [JMIR Publications](https://doi.org/10.2196/resprot.6513).
- This data set contains personal fitness data on thirty FitBit users
  - Minute-level output for physical actiity, heart rate and sleep monitoring
- It is available in the Public Domain (CC0)

Limitations:
- The data only contains records for 30 
Original
Comprehensive
Current
Cited


## Processing the Daily Data



## Analyzing the Daily Data



## Visualizations



## Deliverables and Recommendations



## Appendix - Code

Installing and lthe required packages:

### Setup

Installing and loading the packages:

`
#install.packages("dplyr")
#install.packages("tidyr")
#install.packages("ggplot2")
#install.packages("lubridate")
#install.packages("readr")
#install.packages("janitor")
#install.packages("styler")
library(dplyr)
library(tidyr)
library(ggplot2)
library(lubridate)
library(readr)
library(janitor)
library(styler)
`

Creating a list of csv files in the directory:

`
files_csv <- list.files(path = "bellabeat_data/", pattern = "*.csv")
`

Creating a list of file names for the data frames:

`
files <- substr(files_csv,1,nchar(files_csv)-4)
`

Creating data frames for all the csv files:

`
for(i in files){
  filepath = file.path(paste("bellabeat_data/",i,".csv", sep = ""))
  assign(i,read_csv(filepath))
}
`

Counting the distinct IDs in each data frame to determine how many individuals there were for each data set:

`
n_distinct(dailyActivity_merged$Id)
n_distinct(dailyCalories_merged$Id)
n_distinct(dailyIntensities_merged$Id)
n_distinct(dailySteps_merged$Id)
n_distinct(heartrate_seconds_merged$Id)
n_distinct(hourlyCalories_merged$Id)
n_distinct(hourlyIntensities_merged$Id)
n_distinct(hourlySteps_merged$Id)
n_distinct(minuteCaloriesNarrow_merged$Id)
n_distinct(minuteCaloriesWide_merged$Id)
n_distinct(minuteIntensitiesNarrow_merged$Id)
n_distinct(minuteIntensitiesWide_merged$Id)
n_distinct(minuteMETsNarrow_merged$Id)
n_distinct(minuteSleep_merged$Id)
n_distinct(minuteStepsNarrow_merged$Id)
n_distinct(minuteStepsWide_merged$Id)
n_distinct(sleepDay_merged$Id)
n_distinct(weightLogInfo_merged$Id)
`

All data sets had 33 individuals, except for:
- heartrate_seconds = 14
- minuteSleep = 24
- sleepDay = 24
- WeightLogInfo = 8


### Processing the Daily Data

### Analysing the Daily Data

### Processing the Hourly Data

### Analysing the Hourly Data


## Appendix - Scenario

### Introduction

Welcome to the Bellabeat data analysis case study! In this case study, you will perform many real-world tasks of a junior data analyst. You will imagine you are working for Bellabeat, a high-tech manufacturer of health-focused products for women, and meet different characters and team members. In order to answer the key business questions, you will follow the steps of the data analysis process: ask, prepare, process, analyze, share, and act. Along the way, the Case Study Roadmap tables — including guiding questions and key tasks — will help you stay on the right path.
By the end of this lesson, you will have a portfolio-ready case study. Download the packet and reference the details of this case study anytime. Then, when you begin your job hunt, your case study will be a tangible way to demonstrate your knowledge and skills to potential employers.

### Scenario

You are a junior data analyst working on the marketing analyst team at Bellabeat, a high-tech manufacturer of health-focused products for women. Bellabeat is a successful small company, but they have the potential to become a larger player in the global smart device market. Urška Sršen, cofounder and Chief Creative Officer of Bellabeat, believes that analyzing smart device fitness data could help unlock new growth opportunities for the company. You have been asked to focus on one of Bellabeat’s products and analyze smart device data to gain insight into how consumers are using their smart devices. The insights you discover will then help guide marketing strategy for the company. You will present your analysis to the Bellabeat executive team along with your high-level recommendations for Bellabeat’s marketing strategy

### Characters and products

- Characters
    - **Urška Sršen**: Bellabeat’s cofounder and Chief Creative Officer
    - **Sando Mur**: Mathematician and Bellabeat’s cofounder; key member of the Bellabeat executive team
    - **Bellabeat marketing analytics team**: A team of data analysts responsible for collecting, analyzing, and reporting data that helps guide Bellabeat’s marketing strategy. You joined this team six months ago and have been busy learning about Bellabeat’’s mission and business goals — as well as how you, as a junior data analyst, can help Bellabeat achieve them.
- Products
    - **Bellabeat app**: The Bellabeat app provides users with health data related to their activity, sleep, stress, menstrual cycle, and mindfulness habits. This data can help users better understand their current habits and make healthy decisions. The Bellabeat app connects to their line of smart wellness products.
    - **Leaf**: Bellabeat’s classic wellness tracker can be worn as a bracelet, necklace, or clip. The Leaf tracker connects to the Bellabeat app to track activity, sleep, and stress.
    - **Time**: This wellness watch combines the timeless look of a classic timepiece with smart technology to track user activity, sleep, and stress. The Time watch connects to the Bellabeat app to provide you with insights into your daily wellness.
    - **Spring**: This is a water bottle that tracks daily water intake using smart technology to ensure that you are appropriately hydrated throughout the day. The Spring bottle connects to the Bellabeat app to track your hydration levels.
    - **Bellabeat membership**: Bellabeat also offers a subscription-based membership program for users. Membership gives users 24/7 access to fully personalized guidance on nutrition, activity, sleep, health and beauty, and mindfulness based on their lifestyle and goals.
    
### About the company

Urška Sršen and Sando Mur founded Bellabeat, a high-tech company that manufactures health-focused smart products. Sršen used her background as an artist to develop beautifully designed technology that informs and inspires women around the world. Collecting data on activity, sleep, stress, and reproductive health has allowed Bellabeat to empower women with knowledge about their own health and habits. Since it was founded in 2013, Bellabeat has grown rapidly and quickly positioned itself as a tech-driven wellness company for women.

By 2016, Bellabeat had opened offices around the world and launched multiple products. Bellabeat products became available through a growing number of online retailers in addition to their own e-commerce channel on [their website](https://bellabeat.com/). The company has invested in traditional advertising media, such as radio, out-of-home billboards, print, and television, but focuses on digital marketing extensively. Bellabeat invests year-round in Google Search, maintaining active Facebook and Instagram pages, and consistently engages consumers on Twitter. Additionally, Bellabeat runs video ads on Youtube and display ads on the Google Display Network to support campaigns around key marketing dates.

Sršen knows that an analysis of Bellabeat’s available consumer data would reveal more opportunities for growth. She has asked the marketing analytics team to focus on a Bellabeat product and analyze smart device usage data in order to gain insight into how people are already using their smart devices. Then, using this information, she would like high-level
recommendations for how these trends can inform Bellabeat marketing strategy.

### Ask

Sršen asks you to analyze smart device usage data in order to gain insight into how consumers use non-Bellabeat smart devices. She then wants you to select one Bellabeat product to apply these insights to in your presentation. These questions will guide your analysis:

1. What are some trends in smart device usage?
2. How could these trends apply to Bellabeat customers?
3. How could these trends help influence Bellabeat marketing strategy?

You will produce a report with the following deliverables:

1. A clear summary of the business task
2. A description of all data sources used
3. Documentation of any cleaning or manipulation of data
4. A summary of your analysis
5. Supporting visualizations and key findings
6. Your top high-level content recommendations based on your analysis

Use the following Case Study Roadmap as a guide. Note: Completing this case study within a week is a good goal

|**Case Study Roadmap - Ask**
|---
|**Guiding questions**<br> - What is the problem you are trying to solve?<br> - How can your insights drive business decisions?
|**Key tasks**<br> 1. Identify the business task<br>2. Consider key stakeholders
|Deliverable<br> - A clear statement of the business task

### Prepare

Sršen encourages you to use public data that explores smart device users’ daily habits. She points you to a specific data set:
 - [FitBit Fitness Tracker Data](https://www.kaggle.com/arashnic/fitbit) (CC0: Public Domain, dataset made available through [Mobius](https://www.kaggle.com/arashnic)): This Kaggle data set contains personal fitness tracker from thirty fitbit users. Thirty eligible Fitbit users consented to the submission of personal tracker data, including minute-level output for physical activity, heart rate, and sleep monitoring. It includes information about daily activity, steps, and heart rate that can be used to explore users’ habits.
 
Sršen tells you that this data set might have some limitations, and encourages you to consider adding another data to help address those limitations as you begin to work more with this data.

Now, prepare your data for analysis using the following Case Study Roadmap as a guide:

|**Case Study Roadmap - Prepare**
|---
|**Guiding questions**<br> - Where is your data stored?<br> - How is the data organized? Is it in long or wide format?<br> - Are there issues with bias or credibility in this data? Does your data ROCCC?<br> - How are you addressing licensing, privacy, security, and accessibility?<br> - How did you verify the data’s integrity?<br> - How does it help you answer your question?<br> - Are there any problems with the data?
|Key tasks<br> 1. Download data and store it appropriately.<br>2. Identify how it’s organized.<br>3. Sort and filter the data.<br>4. Determine the credibility of the data.
|**Deliverable**<br> - A description of all data sources used

### Process
Then, process your data for analysis using the following Case Study Roadmap as a guide:
