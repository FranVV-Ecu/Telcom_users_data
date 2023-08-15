# Determination of a prospective tariff for a telecom company<br><br>
## Project Description <br><br>

"Megaline" is a federal operator of cellular communication. Customers are offered two tariff plans: "Smart" and "Ultra". To adjust the advertising budget, the commercial department wants to understand which tariff brings more money.

We need a preliminary analysis of tariffs on a small sample of clients. At the disposal of the data of 500 users of "Megaline": who they are, where they come from, what tariff they use, how many calls and messages each sent in 2018.

We need to analyze customer behavior and make a conclusion - which tariff is better.

## Description of tariffs<br><br>
**Smart tariff**.<br><br>

Monthly fee: 550 rubles
Included 500 minutes of talk time, 50 messages and 15 GB of Internet traffic
Cost of services over and above the tariff package:
one minute of talk time: 3 rubles
message: 3 rubles
1 GB of Internet traffic: 200 rubles

**Tariff "Ultra**<br><br>

Monthly fee: 1950 rubles
Includes 3000 minutes of talk time, 1000 messages and 30 GB of Internet traffic
Cost of services over and above the tariff package:
one minute of talk time: 1 ruble
message: 1 ruble
1 GB of Internet traffic: 150 rubles
WARNING: "Megaline" always rounds up the values of minutes and megabytes. If the user spoke for only 1 second, the whole minute is counted in the tariff.

# Data description <br><br>
### Table users (information about users):

- user_id - unique user identifier<br>
- first_name - user's first name<br>
- last_name - user's last name<br>
- age - user's age (years)<br>
- reg_date - date of tariff connection (day, month, year)<br>
- churn_date - date of tariff termination (if the value is missing, the tariff was still valid at the moment of data upload)<br>
- city - city of user's residence<br>
- tariff - name of tariff plan<br><br>

### Table calls (information about calls):

- id - unique call number<br>
- call_date - date of call<br>
- duration - duration of the call in minutes<br>
- user_id - identifier of the user who made the call<br>

### Table messages (information about messages):

- id - unique message number<br>
- message_date - message date<br>
- user_id - identifier of the user who sent the message<br>

### Table internet (information about internet sessions):

- id - unique session number<br>
- mb_used - amount of Internet traffic spent during the session (in megabytes)<br>
- session_date - date of the Internet session<br>
- user_id - user ID<br>

### Table tariffs (information about tariffs):

- tariff_name - tariff name<br>
- rub_monthly_fee - monthly subscription fee in rubles<br>
- minutes_included - number of minutes of conversation per month included in the subscription fee<br>
- messages_included - number of messages per month included in the subscription fee<br>
- mb_per_month_included - amount of Internet traffic included in the subscription fee (in megabytes)<br>
- rub_per_minute - cost of a minute of talk time in excess of the tariff package (for example, if the tariff includes 100 minutes of talk time per month, then 101 minutes will be charged)<br>
- rub_per_message - cost of sending a message in excess of the tariff package<br>
- rub_per_gb - cost of additional gigabyte of Internet traffic over the tariff package (1 gigabyte = 1024 megabytes).<br><br>

Note. If merging tables using merge method causes dead kernell error, apply join method - it will ease the load on Jupyter Notebook.
