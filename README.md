# SaaS Subscription Payment Funnel Analysis in SQL

[View HEX Data Science Notebook](https://app.hex.tech/big-sql-energy/app/Payment-Funnel-Analysis---SQL-0303lOkrFmrnM8fNaIo20s/latest)

## Executive Summary

The goal of each subscription is to follow the "happy path”, in order to smoothly complete the payment and generate revenue for the company. Using SQL, I track how successful each subscription is throughout the funnel, determining the furthest point they reach before encountering an error or otherwise stopping the process. 

This funnel analysis showed that users are exiting the funnel at several points, so in order to increase workflow completion rate and conversion rates, I recommend the following improvements:

- Improved customer service accessibility
- Proactive client communication from account managers
- Progress-saving functionality

## Business Problem

Successful subscription payments are directly tied to revenue generation for the business. Therefore, it is valuable to ask: Are there any parts of the funnel where users are exiting prior to completion, and where are these friction points? Also, how many users are successfully completing the payment process?

## Methodology

1. Identify the user journeys present in the data.
2. Categorize the subscriptions into their current funnel stage using CASE.
3. Count the subscriptions in each funnel stage and visualize.
4. Calculate key product analytics metrics: Conversion Rate, Workflow Completion Rate, and Error Rate.
5. Analyze results to provide business recommendations.

## Skills

- SQL
  - Joins
  - CTEs
  - Subqueries
  - CASE
- HEX data science notebook
- Snowflake data warehouse
- Data wrangling
- Data visualization

## Results & Business Recommendation

Only 34% of initiated paid subscriptions complete the payment workflow. This low conversion rate indicates that there are friction points within the user journey, which we have identified.

The observed users journeys found in the data are the following: 

- **Happy Path:** Subscription goes smoothly through all five statuses without any errors or returning to previous statuses.
- **User Error w/ Payment Submission:** Subscription has an error after attempting to reach status 3.
- **3rd Party Vendor Error w/ Payment Processing:** Subscription has an error after attempting to reach status 4.
- **Subscriptions Not Even Starting the Payment Process:** Subscriber has not even opened the payment widget, so are not in the payment_status_log table.

![Payment Funnel](https://github.com/RakelFaaland/Payment_Funnel_Analysis/blob/main/Subscription%20Payment%20Funnel.png?raw=true)

After identifying that only 34% of initiated paid subscriptions complete the payment process successfully, I recommend the following changes to increase the workflow completion rate: 

- Implement a visible customer service chat feature at friction points in the payment funnel.
- Improve relationships between account managers and clients to promote payment completion.
- Enable temporary session saves so users can return without losing their progress.

## Next Steps

1. Track workflow completion and conversion metrics before and after new features are implemented.
2. Collect user feedback on site functionality and account manager support to identify remaining friction points.
