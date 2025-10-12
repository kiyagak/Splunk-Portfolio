## Objectives
The goal is to:
- learn what SPL is
- what SPL is used for
- basic SPL commands and real-world use cases
-learn about dashboards
- creating dashboards
- adding panels to existing dashboards

## Filter Data for Date & Time Through the GUI

Click **Apps**, then click **Search and Reporting**:

<img width="1004" height="419" alt="image" src="https://github.com/user-attachments/assets/6ffb62c5-7072-4fb1-b858-4252661e43b1" />

Enter the following search command in the search box:

    index="static-data"

CLick **Search**:

<img width="989" height="639" alt="image" src="https://github.com/user-attachments/assets/2baff874-8cb7-4fb3-818e-12b921429e8e" />

<img width="1122" height="685" alt="image" src="https://github.com/user-attachments/assets/5bbabfbd-0512-43f5-a54a-451e77a18114" />

To view data from the last fifteen minutes
- click **TIme range: Last 24 hours**
- change the time range to **Last 15 minutes**:

<img width="992" height="720" alt="image" src="https://github.com/user-attachments/assets/3c241fb9-d186-4f8e-bfb5-bad497d031e7" />

<img width="992" height="717" alt="image" src="https://github.com/user-attachments/assets/c17b719d-d73f-4cc6-941a-90c848afa74e" />

To view a relative time period
- click the **Time range** button
- click **Relative**
- as an example set it **5 Days Ago** to view data from 5 days ago until now:

<img width="993" height="592" alt="image" src="https://github.com/user-attachments/assets/384a9757-e172-4939-a0d7-3a75d982e5e7" />

To view real-time data
- click the **Time range** button
- click **Real-time**
- as an example set it **7 Hours Ago** to view data from 5 days ago until now

<img width="993" height="539" alt="image" src="https://github.com/user-attachments/assets/898905e5-b18c-4ac6-ac06-0a8bb4f6c6fd" />

Click **Apply**:

<img width="993" height="689" alt="image" src="https://github.com/user-attachments/assets/e4bb52f2-fd82-4a29-b017-92a4d405a52d" />

To view data from a date range
- click the **Time range** button
- click **Date Range**
- as an example set it between **10/07/2025** and **10/08/2025** to view data between October 7th and October 8th of 2025

<img width="993" height="501" alt="image" src="https://github.com/user-attachments/assets/f2b45c0f-676d-40a5-8f88-25220d12e6a1" />

To view data from a date and time range, where time is formatted in **HH:MM:SS.SSS**
- click the **Time range** button
- click **Date & Time Range**
- as an example set it between **10/07/2025 08:00:00.000** and **10/08/2025 12:00:00.000** to view data between October 7th and October 8th of 2025

<img width="993" height="501" alt="image" src="https://github.com/user-attachments/assets/d7efb6d6-c499-44ce-aaf2-2c1c881e2641" />

To view data in an advanced way that shows data from the last 24 hours
- click the **Time range** button
- click **Advanced**
- In the **Earliest** field enter **-24h@h******
- In the **Latest** field enter **now**

<img width="936" height="495" alt="image" src="https://github.com/user-attachments/assets/23aa73f2-1b7d-4b0f-a300-cdce8d5d0048" />

To view data in an advanced way that shows data between the last 2 days and 15 minutes ago
- click the **Time range** button
- click **Advanced**
- In the **Earliest** field enter **-2d@d******
- In the **Latest** field enter **-15m@m**

<img width="936" height="501" alt="image" src="https://github.com/user-attachments/assets/7677689a-4755-4f6c-afe0-6a020e967e80" />


## Filter Data for Date & Time Through SPL Search Parameters

The key [time modifier parameters](https://help.splunk.com/en/splunk-cloud-platform/search/spl2-search-manual/dates-and-time/time-modifiers) that will let you filter searches for specific time periods are
- **earliest**: Specifies the earliest time in the _time field for the time range of your search.
- **latest**: Specifies the latest time in the _time field for the time range of your search. 

Begin your string with a plus (+) or minus (-) to indicate the offset from the current time.  For example to specify a time in the past, a time before the current time, use **minus (-)**.  In addition, you can specify the current time using **now**.  

The [supported time units](https://help.splunk.com/en/splunk-cloud-platform/search/spl2-search-manual/dates-and-time/specifying-relative-time) are listed in the following table.
Time unit | Valid unit abbreviations
--- | ---
second | s, sec, secs, second, seconds
minute | m, min, mins, minute, minutes
hour | h, hr, hrs, hour, hours
day | d, day, days
week | w, week, weeks
month | mon, month, months
quarter | q, qtr, qtrs, quarter, quarters
year | y, yr, yrs, year, years

Search data from the last 5 hours, then click the Search icon:

    index="static-data" earliest=-5h@h latest=now

<img width="973" height="701" alt="image" src="https://github.com/user-attachments/assets/a79fbd0e-6808-469f-8c2a-d20e738a5890" />

## Filter Data by Fields

Filter your search for the top pid value:
- In the left pane click the **pid** field.  
- Under the Top 10 Values column click the top value, which is **1**.

<img width="887" height="699" alt="image" src="https://github.com/user-attachments/assets/a66a65fc-5a7d-405e-a36a-77e3a16e1618" />

<img width="963" height="595" alt="image" src="https://github.com/user-attachments/assets/25702f46-a3fc-4b4b-9d43-fc608d9a39d6" />

Filter your search for the top punct value:
- In the left pane click the **punct** field.  
- Under the Top 10 Values column click the top value, which is

        --::.+:_----_[]:_-.:__.

<img width="887" height="737" alt="image" src="https://github.com/user-attachments/assets/181f4b5a-371c-4ea1-b6a9-84f5d308bcb1" />

<img width="996" height="563" alt="image" src="https://github.com/user-attachments/assets/ae77f31b-429e-43aa-a466-f0fb8db035e4" />

## Use the stats Command

The [**stats**](https://help.splunk.com/en/splunk-cloud-platform/spl-search-reference/10.0.2503/search-commands/stats) command calculates aggregate statistics, such as average, count, and sum, over the results set just like SQL aggregation does.

Search for _interval data:

    index="_internal"

<img width="996" height="861" alt="image" src="https://github.com/user-attachments/assets/22e31c3a-13df-4836-b48b-beddf4798546" />

Choose the name field:

<img width="886" height="894" alt="image" src="https://github.com/user-attachments/assets/df26d6d8-7865-4966-bc78-495a7e5a2073" />

<img width="970" height="358" alt="image" src="https://github.com/user-attachments/assets/c68cfdd0-778c-4d8f-b412-b186ef1b35b6" />

In the search bar enter the following.  Press the SHIFT and ENTER buttons simaltaneously to go to a new line within the search box.  Click **Search** to show each value and how often it is found within that field:

    index="_internal"
    | stats count by name

<img width="970" height="358" alt="image" src="https://github.com/user-attachments/assets/d8457265-065a-468b-a34b-66a85b0bca55" />

<img width="1016" height="557" alt="image" src="https://github.com/user-attachments/assets/24c441cb-5347-4f0a-82f2-6b4849c1ed35" />

Click on the **Visualization** tab to visualize the seach data:

<img width="1016" height="643" alt="image" src="https://github.com/user-attachments/assets/b8256584-e922-4ba3-8961-4ef30e7b823a" />

Change it to a pie chart:

<img width="1010" height="641" alt="image" src="https://github.com/user-attachments/assets/d0406b82-6fd7-4bd0-b36f-525fb42c50f3" />

<img width="1016" height="608" alt="image" src="https://github.com/user-attachments/assets/c5aa9bb9-03f2-4790-ad25-565dbedabea1" />

Remove the **other** value:

<img width="544" height="291" alt="image" src="https://github.com/user-attachments/assets/6692208e-1aa4-413b-959f-fb8e81c6b6d2" />

Click **Format**, then set **Minimum Size** to **0**.  Press the Enter key on your keyboard:

<img width="720" height="389" alt="image" src="https://github.com/user-attachments/assets/c78c8a32-e7a4-46c7-9d92-707705a2cae9" />

<img width="562" height="305" alt="image" src="https://github.com/user-attachments/assets/c98cdc45-4e49-4c98-977c-3ae816cfbfe8" />


## Notes

Difference between chart and timechart:
- chart = 2 fields on X & Y
- timechart = 1 field on Y axis, time on X axis

Cheat Sheets:
- [Create your own search query](http://gosplunk.com)
- [Splunk cheat sheet](https://www.splunk.com/en_us/blog/learn/splunk-cheat-sheet-query-spl-regex-commands.html)
- [Splunk cheat sheet PDF](https://www.splunk.com/en_us/pdfs/solution-guide/splunk-quick-reference-guide.pdf)

## What I Learned
