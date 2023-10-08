# Homework 1: Professionalism & Reproducibility
## DATA512 Human Centered Data Science: Wikipedia Pageview analysis
## Goal

The goal of this project is to create a Python script that retrieves and analyzes pageviews data from the Wikimedia API for a list of Wikipedia articles. The script aims to provide insights into the pageviews trends for these articles, including:
1. Maximum Average and Minimum Average - The first graph should contain time series for the articles that have the highest average monthly page requests and the lowest average monthly page requests for desktop access and mobile access. Your graph should have four lines (max desktop, min desktop, max mobile, min mobile).
2. Top 10 Peak Page Views - The second graph should contain time series for the top 10 article pages by largest (peak) page views over the entire time by access type. You first find the month for each article that contains the highest (peak) page views, and then order the articles by these peak values. Your graph should contain the top 10 for desktop and top 10 for mobile access (20 lines).
3. Fewest Months of Data - The third graph should show pages that have the fewest months of available data. These will all be relatively short time series and should contain a set of the most recent academy award winners. Your graph should show the 10 articles with the fewest months of data for desktop access and the 10 articles with the fewest months of data for mobile access.

## Data Source

The data for this project is sourced from the Wikimedia API, which provides access to a wide range of information related to Wikipedia articles and their pageviews. Specifically, we use the "pageviews" endpoint of the Wikimedia API to retrieve pageviews data for a selected list of Wikipedia articles.

- **API Endpoint:** [Wikimedia Pageviews API](https://wikimedia.org/api/rest_v1/metrics/pageviews/)

The API allows us to specify various parameters such as the project (e.g., "en.wikipedia.org" for English Wikipedia), access type (e.g., "desktop" and "mobile"), article name, granularity of data (e.g., "monthly"), and date range. It returns JSON-formatted data containing pageviews information for the specified articles and parameters.
