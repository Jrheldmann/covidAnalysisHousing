# Starfall
00-team-01 Group Project Final

### 12/7/2022 - In-class meeting notes
- Tim needs to look into a missing calendar request from Juhi – need to allow permissions for everyone
    - Resolved during meeting – invites for full calendar permissions sent via email
- ACS demographic data not avail for 2022 yet; can use 1 year dataset for 2021, 5 year dataset for 2017-2020
    - Everyone: continue searching for 2022 data from other potential sources
- For deliverables, let’s have them done for Mondays/Tuesdays so that we can review any issues before needing to submit on Wednesdays
- Compiling data sources still in progress; Juhi will compile links we’ve put in Slack and some others she’s found; everyone post any additional links in Slack
- Will is setting up about 4 provisional models for us to use dummy data for testing as 1st segment deliverable
    - Discussed keeping the coding in Google Collab rather than Jupyter Notebook as per recommendation from Dave & Arin
- AZ mentioned his group breaking further into pairs for work; we think that doing the same once we get into the detail-oriented work of data cleaning would be a good idea for getting multiple sets of eyes on each set of work as we go
- Discussed concern about whether Zillow can be considered an authoritative number for real estate
    - Appears it should be, as many of what we thought might be “competitors” are actually subsidiaries
- Started discussing some of the issues that we anticipate in data cleaning:
    - Can see we have plenty of empty rows
    - There are NINE codes in ACS data for county “urban-ness”; we likely want to collapse those down to perhaps three (urban, suburban, rural)
    - County names have a number of issues surrounding them:
        - different naming conventions between government sources vs. Zillow
        - duplicate county names across different states
        - spelling inconsistencies

### 12/5/2022 – In-class meeting notes
- Tim will take notes for each session so we’re all on the same page. Will post to Slack, GitHub readme for everyone to reference as needed
- Team name proposed and agreed on: Starfall
- Pivoting topic from using weather as geographic predictor of increasing Covid cases --> using Covid cases as geographic predictor of increasing home sales
- Scheduling & contact info:
    - Tim will create and share a Google calendar; will post dates people have said they are unavailable for potential meetings, everyone should be able to update the calendar with any more scheduling blackouts as individual conflicts arise
    - General weekday work schedules:
        - Joe & Will work 7-3
        - Juhi works 9-5
        - Tim’s schedule is 24/7 ever-changing chaos as a caregiver, but can generally arrange to be available for meetings/coordinating on any tasks at most times, feel free to contact via text whenever and he can at least respond to keep informed within a half hour
    - Phone numbers:
        - Joe: 908-XXX-XXXX
        - Juhi: 908-XXX-XXXX
        - Tim: 973-XXX-XXXX
        - Will: 732-XXX-XXXX
- Current to do list for each of our roles (named as per the course module):
    - Joe (square): GitHub structure setup and sharing
        - Github usernames:
            - Joe: Jrheldmann
            - Juhi: aggarwaljuh
            - Tim: tfish110
            - Will: willenny
    - Juhi (circle): Database structure mockup
    - Tim (X): Calendar setup, checking out early quick & dirty data viz in Tableau
    - Will (triangle): prelim model setup
    - All: start getting more acquainted with the datasets available from the links we’ve put in slack from CDC, Census Bureau, Zillow
        - Remember to keep in mind that some of the raw data will need to be standardized, i.e. if one dataset is split into cities and another is split into counties, we will eventually need to group the city-based variables into their respective counties. We should be able to automate this process during data cleaning with a few lines of code.
        - Late in the meeting we discussed the importance of using housing data from years both pre-Covid AND post-Covid to make a case for home-buying behavior changing when Covid was introduced as a variable, so please keep that in mind when familiarizing ourselves with the datasets.