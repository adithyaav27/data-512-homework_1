# Homework 1: Professionalism & Reproducibility
## DATA512 Human Centered Data Science: Wikipedia Pageview analysis
## Goal

The goal of this project is to create a reproducible python script that retrieves and analyzes pageviews data from the Wikimedia API for a list of Wikipedia articles. The script aims to provide insights into the pageviews trends for these articles, including:
1. Maximum Average and Minimum Average - The first graph should contain time series for the articles that have the highest average monthly page requests and the lowest average monthly page requests for desktop access and mobile access. Your graph should have four lines (max desktop, min desktop, max mobile, min mobile).
2. Top 10 Peak Page Views - The second graph should contain time series for the top 10 article pages by largest (peak) page views over the entire time by access type. You first find the month for each article that contains the highest (peak) page views, and then order the articles by these peak values. Your graph should contain the top 10 for desktop and top 10 for mobile access (20 lines).
3. Fewest Months of Data - The third graph should show pages that have the fewest months of available data. These will all be relatively short time series and should contain a set of the most recent academy award winners. Your graph should show the 10 articles with the fewest months of data for desktop access and the 10 articles with the fewest months of data for mobile access.

## Data Source License
- **License:**[Wikimedia Terms of use](https://www.mediawiki.org/wiki/API:REST_API#Terms_and_conditions) 

## API
The data for this project is sourced from the Wikimedia API, which provides access to a wide range of information related to Wikipedia articles and their pageviews. Specifically, we use the "pageviews" endpoint of the Wikimedia API to retrieve pageviews data for a selected list of Wikipedia articles.

- **WIKI API Endpoint:** [Wikimedia Pageviews API](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews)
- **Python requests module:** [Python requests module](https://pypi.org/project/requests/)

## Data Files
### Inputs:
- **thank_the_academy.AUG.2023.csv.xlsx**: This contains the full list of titles which the code pulls page view data for.

### Outputs:

- **academy_monthly_mobile_201507-202309.json**: This JSON file contains monthly pageviews data for articles accessed via mobile devices which is the sum of mobile web and mobile app.
   - **Fields:**
     - `name`: The name of the Wikipedia article.
     - `timestamp`: The timestamp representing the month and year of the data (e.g., "202301" for January 2023).
     - `views`: The number of pageviews for the article during that specific month.

- **academy_monthly_desktop_201507-202309.json**: This JSON file contains monthly pageviews data for articles accessed via desktop.
   - **Fields:**
     - `article name`: The name of the Wikipedia article.
     - `timestamp`: The timestamp representing the month and year of the data (e.g., "202301" for January 2023).
     - `views`: The number of pageviews for the article during that specific month.
     - We get other fileds like `project` (source), `granularity` (monthly, yearly, etc.), `access` (desktop, mobile, etc.) & `agent` (user, etc.).

- **academy_monthly_cumulative_201507-202309.json**: This JSON file contains monthly cumulative pageviews data for Wikipedia articles, which is the sum of mobile and desktop views.
   - **Fields:**
     - `name`: The name of the Wikipedia article.
     - `timestamp`: The timestamp representing the month and year of the data (e.g., "202301" for January 2023).
     - `views`: The number of cumulative pageviews (mobile + desktop) for the article during that specific month.

### Visualization Outputs:

- **MaximumMinimumAverage.png**: This PNG file is a graph showing the monthly page views of the most and least viewed articles on both mobile and desktop platforms.
- **Top10PeakPageViews.png**: This PNG file is a graph showing the monthly page views of the top 10 articles with the highest peak monthly views.
- **FewestMonths.png**: This PNG file is a graph showing the monthly page views of the top 10 articles with the fewest months of data available.


## Known Issues and Special Considerations
1. The Date range to pull the data has to specified in `ARTICLE_PAGEVIEWS_PARAMS_TEMPLATE`. This is not dynamic.
2. The data collection process might be slighty time consuming as we will be calling the API for more than 1000 times.
3. Rate Limiting and Throttling has to be kept in mind to avoid being temporarily blocked.
