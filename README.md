# WattWise Energy Analytics: Energy Consumption and Forecasting

# ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)


## Project Overview

WattWise Energy Analytics is a group data analytics project that explores household electricity consumption using historical electricity usage data.

The project investigates how electricity consumption changes by hour, day, month and year. It also explores periods of high electricity demand, relationships between electrical measurements and opportunities for forecasting future consumption.

Our team used Python, data analysis libraries, Jupyter Notebooks and interactive visualisation tools to prepare, analyse and present the data. The findings are presented through visualisations and an interactive dashboard to help users understand household electricity usage.

## Project Objectives

The main objectives of the project were to:

- Explore household electricity consumption patterns over time.
- Identify periods of high and low electricity demand.
- Compare consumption across different hours, days, months and years.
- Investigate relationships between electrical measurements.
- Explore seasonal patterns and forecasting opportunities.
- Communicate findings through clear visualisations and interactive dashboards.

## Dataset

Our project uses the [Individual Household Electric Power Consumption dataset on Kaggle](https://www.kaggle.com/datasets/uciml/electric-power-consumption-data-set), which originates from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/235/individual+household+electric+power+consumption).

The original dataset contains approximately 2.07 million records of household electricity measurements collected at one-minute intervals between December 2006 and November 2010.

To make the data more manageable, our team aggregated the minute-level readings into hourly averages.

The data reduction process produced 34,589 expected hourly records. Following further cleaning, the dataset used for exploratory data analysis contained 34,168 records and seven electrical measurement columns.

### Main Dataset Variables

| Variable | Description |
|---|---|
| `global_active_power` | Household active power consumption, measured in kilowatts (kW). |
| `global_reactive_power` | Household reactive power consumption, measured in kilowatts (kW). |
| `voltage` | Average voltage, measured in volts (V). |
| `global_intensity` | Average current intensity, measured in amperes (A). |
| `sub_metering_1` | Energy recorded by sub-metering system 1, in watt-hours (Wh). |
| `sub_metering_2` | Energy recorded by sub-metering system 2, in watt-hours (Wh). |
| `sub_metering_3` | Energy recorded by sub-metering system 3, in watt-hours (Wh). |

**Important:** The dataset represents one household. Our findings therefore describe the recorded household and should not automatically be generalised to all households or geographical regions.

## Business Requirements

The project addressed the following business requirements:

1. **Understand electricity consumption patterns:** Explore how household electricity usage changes over time.
2. **Identify peak consumption periods:** Find the hours, days and months associated with higher electricity consumption.
3. **Investigate seasonal patterns:** Explore changes in electricity usage across different seasons and years.
4. **Understand relationships between measurements:** Examine relationships between active power, reactive power, voltage, current intensity and sub-metering measurements.
5. **Explore forecasting opportunities:** Investigate whether historical consumption patterns could support future forecasting.
6. **Communicate useful insights:** Present findings through visualisations and dashboards to support better understanding of household energy usage.

## Data Preparation and Analysis Workflow

Our team followed a structured process to prepare and analyse the dataset.

1. **Data collection:** Obtained the original household electricity consumption dataset through Kaggle and identified its UCI source.
2. **Data reduction:** Aggregated minute-level readings into hourly averages to make the data easier to process and analyse.
3. **Data cleaning:** Converted measurement columns to numeric values, checked date and time information, handled invalid entries and examined duplicate records.
4. **Data quality checks:** Investigated missing values and gaps in the hourly timestamps.
5. **Exploratory data analysis:** Examined consumption patterns, summary statistics and relationships between measurements.
6. **Visualisation:** Created charts to communicate patterns and findings.
7. **Dashboard development:** Developed interactive dashboard features to support further exploration of the data.
8. **Documentation and version control:** Organised project files, documented the work and managed project updates through GitHub.

## Research Methodology and Analysis Techniques

We used a quantitative approach because the project focuses on numerical electricity measurements collected over time.

### Data Reduction and Cleaning

We used Pandas to load, clean, transform and aggregate the dataset. Reducing the original minute-level records to hourly averages made the data more manageable while retaining useful consumption patterns.

We also examined data types, invalid entries, duplicate timestamps and missing observations.

### Exploratory Data Analysis (EDA)

Exploratory Data Analysis helped us understand the structure, quality and patterns within the dataset before interpreting the results.

Our analysis included:

- Inspecting the number of rows and columns, data types and date range.
- Identifying missing values and duplicate timestamps.
- Checking gaps in the expected hourly observations.
- Exploring hourly, daily, weekly and monthly consumption patterns.
- Comparing average consumption by hour, day of the week, month and year.
- Examining relationships between electrical measurements.
- Exploring seasonal patterns and forecasting opportunities.

### Descriptive Statistics

We used summary statistics, including averages and other descriptive measures, to compare electricity consumption across different periods.

### Correlation Analysis

We examined relationships between electrical measurements using correlation analysis and visualisations.

A correlation coefficient ranges from -1 to +1. Positive values indicate that two variables tend to move in the same direction, while negative values indicate that they tend to move in opposite directions.

Correlation does not prove causation, so the results must be interpreted carefully.

### Statistical Hypotheses

Our team identified three hypotheses for further statistical investigation:

**Hypothesis 1: Weekday and Weekend Consumption**

- Null hypothesis (H0): There is no statistically significant difference in mean active power consumption between weekdays and weekends.
- Alternative hypothesis (H1): Mean active power consumption differs between weekdays and weekends.

**Proposed method:** An independent two-sample t-test allowing for unequal variances.

**Hypothesis 2: Evening Peak and Off-Peak Consumption**

- Null hypothesis (H0): Mean active power consumption during evening peak hours (18:00–22:00) is equal to consumption during other hours.
- Alternative hypothesis (H1): Mean active power consumption during evening peak hours is greater than consumption during other hours.

**Proposed method:** A statistical comparison of evening peak and other hourly readings.

**Hypothesis 3: Active Power and Global Intensity**

- Null hypothesis (H0): There is no statistically significant linear relationship between global active power and global intensity.
- Alternative hypothesis (H1): There is a statistically significant positive linear relationship between global active power and global intensity.

**Proposed method:** Pearson correlation analysis.

These hypotheses formed part of the team's proposed statistical investigation. They should not be interpreted as confirmed statistical findings or conclusions.

### Time-Series Analysis and Forecasting

We explored consumption patterns over time and used seasonal decomposition to examine trend, seasonal patterns and irregular variation.

The Streamlit application also includes an exploratory forecasting feature using Prophet. Forecasts are intended to support further investigation of possible future consumption patterns.

The forecasting feature should be treated as exploratory because a documented held-out evaluation of predictive performance was not completed.

## Key Exploratory Findings

Our exploratory analysis identified several patterns in the household electricity data:

- **Seasonal consumption:** Average electricity consumption was generally higher in December and January, while July and August showed lower average consumption.
- **Hourly consumption:** Consumption was generally lowest during the early morning hours, particularly around 03:00–05:00, and higher around 20:00, with a smaller morning increase around 07:00.
- **Weekend patterns:** The exploratory comparison showed higher average consumption on Saturdays and Sundays than on weekdays.
- **Relationships between measurements:** Global active power and global intensity showed a strong positive correlation, while voltage and active power showed a negative correlation.
- **Missing observations:** The hourly dataset contained 421 missing expected observations, representing approximately 1.22% of the 34,589 expected hourly records.

These findings describe the available dataset. Missing observations and incomplete coverage at the beginning and end of the recording period may affect some comparisons, particularly year-to-year analysis.

## Visualisation Rationale

We selected visualisations according to the business questions they were intended to answer.

| Business question | Visualisation | Purpose |
|---|---|---|
| How does consumption change over time? | Time-series line chart | Shows changes, peaks and drops in electricity consumption. |
| Which hours have higher demand? | Bar chart of average consumption by hour | Makes hourly consumption patterns easier to compare. |
| How does consumption differ across days? | Day-of-week comparison chart | Shows differences between weekdays and weekends. |
| Are there seasonal patterns? | Monthly and yearly charts | Helps identify changes across months and years. |
| How are electrical measurements related? | Correlation heatmap and scatter plots | Shows relationships between different measurements. |
| Can users explore different periods? | Interactive dashboard filters and charts | Allows users to examine selected dates and measurements. |
| Can historical patterns support forecasting? | Seasonal decomposition and forecast visualisations | Helps explore trends and possible future consumption patterns. |

## Dashboard Development

Our team developed visualisations and dashboard features to make the analysis easier to explore.

### Tableau Dashboard

The published Tableau dashboard presents the WattWise Energy Analytics findings.

**[View the WattWise Energy Analytics Tableau Dashboard](https://public.tableau.com/app/profile/oluwaseun.olasupo/viz/WattWiseEnergyAnalytics/WattWisedashboard)**

### Streamlit Application

The project repository also contains a Python-based Streamlit application in `app.py`.

The application includes:

- Date range and measurement filters.
- Time-of-day, season and sub-metering selections.
- Summary indicators for electricity consumption.
- Consumption trends and distribution charts.
- Hourly and weekday consumption patterns.
- Visualisations comparing electrical measurements.
- An exploratory Prophet forecasting feature.
- Energy consumption insights and recommendations.

The application can be run locally using the instructions below.

## Repository Contents

The repository contains the main project files and supporting analysis.

| File or folder | Description |
|---|---|
| `app.py` | Streamlit dashboard application. |
| `requirements.txt` | Python packages required by the dashboard application. |
| `README.md` | Project documentation. |
| `cleaned_data_power_consumption.txt` | Cleaned dataset used by the dashboard. |
| `reduced_data.txt` | Reduced dataset created during data preparation. |
| `transformed_data_power_consumtion.txt` | Transformed dataset used during the analysis workflow. |
| `jupyter_notebooks/` | Folder containing the project's Jupyter Notebooks. |
| `jupyter_notebooks/reduced_data_code.ipynb` | Notebook for reducing the original dataset. |
| `jupyter_notebooks/cleaned data code.ipynb` | Notebook for cleaning the data. |
| `jupyter_notebooks/update_of_the_transformed_data.ipynb` | Notebook for updating transformed data. |
| `jupyter_notebooks/EDA.ipynb` | Notebook containing exploratory data analysis. |
| `jupyter_notebooks/hypothesis_statistical_testing.ipynb` | Notebook allocated to hypothesis testing. |

## Tools and Technologies

| Tool or library | Purpose |
|---|---|
| Python | Main programming language for data analysis and application development. |
| Jupyter Notebook | Organising and documenting analysis steps. |
| Pandas | Loading, cleaning, transforming and aggregating data. |
| NumPy | Supporting numerical operations. |
| Matplotlib and Seaborn | Creating data visualisations. |
| Plotly | Creating interactive charts. |
| Streamlit | Developing the interactive Python dashboard. |
| Prophet | Supporting exploratory time-series forecasting. |
| Statsmodels and SciPy | Supporting statistical and time-series analysis where used. |
| GitHub | Version control, collaboration and project documentation. |
| Tableau Public | Publishing the interactive data visualisation dashboard. |

## Known Limitations

The project has several limitations that should be considered when interpreting the findings:

- **Single-household dataset:** The data represents one household and cannot automatically represent the consumption habits of other households.
- **Missing hourly observations:** The cleaned dataset contains 421 missing expected hourly observations out of 34,589.
- **Incomplete time coverage:** The beginning and end of the dataset have incomplete calendar coverage, which can affect some yearly comparisons.
- **Data aggregation:** Converting minute-level readings into hourly averages removes some short-term consumption changes.
- **Correlation:** Relationships between measurements do not establish cause and effect.
- **Forecasting:** The forecasting feature is exploratory and has not been supported by a documented held-out performance evaluation.
- **Statistical testing:** The proposed hypotheses should not be presented as statistically confirmed without completed tests and recorded results.

## Ethical Considerations

The dataset contains household electricity measurements rather than direct personal identifiers. However, detailed electricity usage patterns may reveal information about household routines and occupancy.

Our project considers the following issues:

- **Privacy:** We avoid attempting to identify the household or infer personal details beyond what the data supports.
- **Responsible interpretation:** We do not present one household's consumption patterns as representative of all households.
- **Data quality:** We acknowledge missing observations and explain how data quality may affect the analysis.
- **Transparency:** We identify the data source, explain the methods and acknowledge limitations.
- **Responsible use of AI:** AI-assisted suggestions and outputs should be reviewed and checked rather than accepted without verification.

The dataset was used for educational analysis.

## Use of Generative AI

Generative AI tools were used as supporting resources during the project where applicable. They can assist with understanding Python concepts, exploring ideas, reviewing code, improving documentation and considering ways to communicate analytical findings.

AI-generated suggestions are not treated as verified results. The team remains responsible for reviewing code, checking outputs against the dataset and ensuring that the final analysis and explanations are accurate.

## Running the Streamlit Application Locally

To run the dashboard locally:

1. Clone the repository:

   ```bash
   git clone https://github.com/Mumtazib01/wattwise-energy-analytics.git
   ```

2. Open the project folder:

   ```bash
   cd wattwise-energy-analytics
   ```

3. Create and activate a virtual environment if required.

4. Install the dashboard dependencies:

   ```bash
   pip install -r requirements.txt
   ```

5. Make sure `cleaned_data_power_consumption.txt` is available in the project root folder.

6. Start the Streamlit application:

   ```bash
   streamlit run app.py
   ```

**Note:** The original raw dataset may need to be downloaded separately. Some notebook file paths may also need adjusting to match the location of the project on your computer.

## Credits and Acknowledgements

### Dataset Sources

- [Kaggle – Electric Power Consumption Dataset](https://www.kaggle.com/datasets/uciml/electric-power-consumption-data-set): The platform through which our team accessed the dataset.
- [UCI Machine Learning Repository – Individual Household Electric Power Consumption](https://archive.ics.uci.edu/dataset/235/individual+household+electric+power+consumption): The original dataset source.

### Technical Resources

We acknowledge the official documentation and learning resources that supported the project:

- [Pandas](https://pandas.pydata.org/docs/)
- [NumPy](https://numpy.org/doc/)
- [Matplotlib](https://matplotlib.org/stable/)
- [Seaborn](https://seaborn.pydata.org/)
- [Plotly](https://plotly.com/python/)
- [Streamlit](https://docs.streamlit.io/)
- [Prophet](https://facebook.github.io/prophet/)
- [SciPy](https://docs.scipy.org/doc/scipy/)
- [Statsmodels](https://www.statsmodels.org/stable/index.html)
- [GitHub](https://docs.github.com/)
- [Code Institute](https://codeinstitute.net/)

### Acknowledgements

We would like to thank:

- **The dataset providers:** The University of California, Irvine (UCI) Machine Learning Repository and Kaggle for making the household electricity consumption data accessible.
- **Code Institute:** For providing the learning resources, project brief and hackathon guidance.
- **Our team members:** For their collaboration, individual contributions, shared ideas and commitment throughout the four-day hackathon.
- **Tools and technologies:** For providing the resources used to prepare, analyse and present the data.

This project represents a collaborative learning experience in data preparation, exploratory analysis, visualisation, dashboard development, forecasting exploration and teamwork.




