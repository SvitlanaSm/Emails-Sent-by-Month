# Emails-Sent-by-Month
## Description
This SQL query calculates **each account’s contribution** to the total number of emails sent within a given month. It uses advanced **window functions** and date manipulation to segment user activity and compute engagement metrics at the monthly level.

## Key Metrics Calculated
* `sent_month`: The month when emails were sent, calculated by shifting session dates using an offset (sent_date)

* `id_account`: The account that sent the emails

* `msg_cnt_account`: The number of messages sent by a specific account in a given month

* `msg_cnt_month`: The total number of messages sent by all accounts during that month

* `sent_cnt_percent`: The percentage of monthly emails that were sent by the account

* `first_sent_date`: The first email send date by the account in that month

* `last_sent_date`: The last email send date by the account in that month

## Logic Overview
1. **Window functions*** are used to calculate counts and date ranges:

`COUNT()` over partitions for per-account and per-month email volumes

`MIN()` and `MAX()` to find first and last activity dates

2. **DATE_ADD** and **DATE_TRUNC** adjust and standardize dates for monthly aggregation

3. **Percentage metric** is computed to show account-level contribution  

## Data Sources  
  
`email_sent`: contains email send events with relative send date offsets

`account_session`: links sessions to accounts

`session`: contains base session date information
