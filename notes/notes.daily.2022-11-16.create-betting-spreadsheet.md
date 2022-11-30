---
id: 0c44flimx5xp91rydysf4f6
title: Create a Betting Spreadsheet
desc: 'Create a Betting Spreadsheet'
updated: 1669812382356
created: 1669576718969
---
# Create a Betting Spreadsheet

After having learned [[how to read odds|notes.daily.2022-11-16.football-betting]], I want to practice the experience of betting. Hence, I organized a betting event for World Cup 2022. I use Google Sheets to manage this event. This note summarized this enjoyable experience.

## How did I organize the spreadsheet?

### Import data into Google Sheets from 3rd party API provider

I consulted these 2 tutorials:
- [api-football | Import sports data in Google Sheets with SyncWith](https://www.api-football.com/news/post/import-sports-data-in-google-sheets-with-syncwith)
- [tryamigo | Import Football Data To Google Sheets](https://blog.tryamigo.com/import-football-data-to-google-sheets/)

Automate the spreadsheet with these Google Sheets addon
- [SyncWith | Any API](https://workspace.google.com/marketplace/app/syncwith_any_api/449644239211)
    - I used this addon for the experiment
- [Amigo: Data Exports and Reports](https://workspace.google.com/marketplace/app/amigo_data_exports_and_reports/274781802717)
- [LogicSheet](https://logicsheet.co/)
- [API Connector by Mixed Analytics](https://workspace.google.com/marketplace/app/api_connector/95804724197)
    - pros: has custom function [ImportAPI](https://mixedanalytics.com/knowledge-base/importapi-custom-sheets-function/)

API service provider
- [sportradar](https://developer.sportradar.com/)
    - [Soccer v4 API document](https://developer.sportradar.com/docs/read/football_soccer/Soccer_v4)
    - I tested their API service at this [Interactive API](https://developer.sportradar.com/io-docs) page
- [api-football](https://www.api-football.com/)
    - This service use login auth provided by [rapidapi](https://rapidapi.com/api-sports/api/api-football/pricing), where I failed to sign up via email. So I didn't have a chance to test this.

Which data do I need?
- datetime of match
- name of each participated team
- match score

After having read the [Soccer v4 API document](https://developer.sportradar.com/docs/read/football_soccer/Soccer_v4) from sportradar, I understand that these basic match information can be accessed at [Season Schedule feed](https://developer.sportradar.com/docs/read/football_soccer/Soccer_v4#season-schedule).

Then I use [SyncWith | Any API](https://workspace.google.com/marketplace/app/syncwith_any_api/449644239211) to import this feed into my spreadsheet.

### Use QUERY function to automate the data entry steps

I used the [[notes.tutorial.google-sheets-excel.function.query]] to automate some steps in the data entry part.

The trick includes:
- filter data with datetime format
- filter data which contain a specific string
- use nested query to avoid creating a helper-column

## What fun did I learn with the betting experience?

The rate of return (~50%) from the [[Asian handicap betting style|notes.daily.2022-11-16.football-betting#asian-handicap-style]] are quite low compared to the rate (~85%) obtained with [[European style|notes.daily.2022-11-16.football-betting#european-style]].

Sport betting is illegal in Vietnam, the only way to promote the presence of a betting exchange is the ads banner on many pirated content websites (movie, manga, novel).

Sport betting in Vietnam is a lucrative business but not legal (yet). I expect that Vietnam can learn the practice from the developed countries (eg. US, Europe), and open an official betting market in the near future.