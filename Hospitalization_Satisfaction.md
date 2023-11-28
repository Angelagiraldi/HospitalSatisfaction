# Hospital performance

## A comprehensive analysis of HCAHPS survey outcomes to assess healthcare quality and explore possible improvements

*The following project is based on the [Maven’s Healthcare Challenge](https://mavenanalytics.io/challenges/maven-healthcare-challenge/26).*

Operating under the American Hospital Association (AHA), this project rigorously evaluates the Hospital Consumer Assessment of Healthcare Providers and Systems (HCAHPS) survey results over the past 9 years (2013-2022).

HCAHPS surveys serves as a standardize instrument for understanding patient perceptions of hospital care  and have the goal to "create incentives for hospitals to improve their quality of care".

Here only few of the many questions I have tried to answer:

* Have hospitals' HCAHPS scores improved over the past 9 years?
* Are there any specific areas where hospitals have made more progress than others?
* Are there any major areas of opportunity remaining?
* What recommendations can you make to hospitals to help them further improve the patient experience?

Read below to know more!

---------------------------------

Here an outline of the project:

1) [About the data set](#dataset)
2) Exploratory analysis (EDA)
3) Regression analysis
4) Insights & recommendations


## About the data set <a name="dataset"></a>
The data includes several separate datasets at national & state-level, including hospital-level completions and response rates, from 2013 to 2022 for the Hospital Consumer Assessment of Healthcare Providers and Systems (HCAHPS) survey. 

In particular the 7 different available datasets are:
*  **Reports**
    - Release Period (PK): Uniquely identifies each HCAHPS report, specifying the date (month_year) of data release
    - Start Date & End Date: Define certain time frames when the patients were discharged and that are taken into account for each report release.

* **States**
    - State & State Name: Presents state abbreviations and full names for the 50 US States, along with the District of Columbia (DC).
    * Region: Groups states as per the United States Census Bureau classification.

* **National & State Results** 
    - Release Period: Links data rows to specific HCAHPS reports.
    - Measure ID: Connects data rows to respective measures.
    - Bottom-box Percentage, Middle-box Percentage, Top-box Percentage: Indicates respondent percentages per box category (least positive, intermediate, most positive) at national and state levels.

* **Responses**
    - Release Period, State, Facility ID: Correlates data rows with specific HCAHPS reports, states, and unique hospital identifiers.
    - Completed Surveys: Quantifies the number of patient-discharged surveys completed by each facility in a given report.
    - Response Rate (%): Represents survey submission rates as a percentage, reflecting patient engagement.

* **Measures**
    - Measure ID & Measure: Uniquely identifies each HCAHPS measure, derived from specific survey questions, providing descriptions for each measure.
    - Type: Classifies measures into "Composite measures" (comprised of multiple survey questions) and "Individual Items" or "Global Items" (tied to single questions).

* **Questions**
    - Question Num: Sequential numbering as seen on the HCAHPS patient survey.
    - Measure ID (FK): Establishes the relationship between questions and measures.
    - Question: Reflects the survey question presented to patients
    - Bottom-box Answer, Middle-box Answer, Top-box Answer: Categorizes responses into least positive, intermediate, and most positive, respectively.


There are important measures in the dataset and each show how patients feel and important parts of the patient experience in healthcare centres. Here is the complete list of measures:

1) **H_Comp_1** Communication with nurses
2) **H_Comp_2** Communication with doctors
3) **H_Comp_3** Responsiveness of hospital staff
4) **H_Comp_5** Communication about medicines
5) **H_Comp_6** Discharge information
6) **H_Comp_7** Care transition
7) **H_Clean_HSP** Cleanliness of hospital environment
8) **H_Quiet_HSP** Quietness of hospital environment
9) **H_HSP_Rating** Overall hospital rating
10) **H_RECMND** Willingness to recommend hospital