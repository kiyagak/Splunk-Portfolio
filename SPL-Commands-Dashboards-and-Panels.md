## Objectives

The goal is to:
- learn what SPL is
- what SPL is used for
- basic SPL commands and real-world use cases
-learn about dashboards
- creating dashboards
- adding panels to existing dashboards

## What is SPL?

[SPL](https://docs.splunk.com/Splexicon:SPL) is the abbreviation for the Splunk Search Processing Language. The Search Processing Language is a set of commands that you use to search your data. 

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

## Transformation Commands

The main transformation commands that transform data are:
- stats
- timechart
- chart

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

How to sort stats command data in ascending order:

    index="_internal"
    | stats count by name
    | sort count

<img width="961" height="602" alt="image" src="https://github.com/user-attachments/assets/ee0e3233-cbc9-4958-9642-04a1ae098d70" />

How to sort stats command data in descending order:

    index="_internal"
    | stats count by name
    | sort - count
    
<img width="961" height="522" alt="image" src="https://github.com/user-attachments/assets/ab00f694-d055-4637-9502-9fe26ea44f73" />

How to rename the fields output by the stats command data:

	index="_internal"
	| stats count by name
	| sort - count
	| rename name as "Values of Name" count as "Number of Logs"

<img width="961" height="615" alt="image" src="https://github.com/user-attachments/assets/90b7bd61-b93b-4824-b217-4972cceb5513" />

## Differences Between the chart and timechart Commands

Use cases for timechart and chart commands:
- timechart:
    - Used for automatic, easy aggregation and visualization of event counts or metrics over time intervals.
    - It has one field on the Y axis
    - It has time on the X axis
- chart:
    - Used to aggregate and group by non-time fields or need a generic summary table without automatic time bucketing.
    - It has two fields, each on an X and Y axis.  

## Use the timechart Command

[**timechart**](https://help.splunk.com/en/splunk-enterprise/search/spl-search-reference/9.4/search-commands/timechart) is a search command that creates a time series chart with corresponding table of statistics.  By default i lists out the top 10 values of a field separated by 30 minute segments:  

    index="_internal"
    | timechart count by source

<img width="1202" height="647" alt="image" src="https://github.com/user-attachments/assets/474e8e46-888b-447a-9263-ffd7c37396de" />

Edit the timespan of each time block to be one hour:

	index="_internal"
	| timechart span=1h count by source

<img width="1202" height="647" alt="image" src="https://github.com/user-attachments/assets/db699a4e-ec6b-489e-8c95-f65802791177" />

Visualize the time chart:
- Click the **Visualization** tab.
- Click the **Chart** button.
- Choose a **Line Chart** or **Area Chart**.

<img width="1202" height="622" alt="image" src="https://github.com/user-attachments/assets/b9e7c503-95bd-469e-911b-23134d15e6bc" />

<img width="1195" height="552" alt="image" src="https://github.com/user-attachments/assets/10e978ca-2c6e-47ff-8143-abf3b2d87a87" />

How to use the timechart command with multiple fields.  Click on the **Statistics** tab after entering the query:

	index="_internal"
	| chart count over log_level by host

<img width="968" height="552" alt="image" src="https://github.com/user-attachments/assets/84d6b141-e669-4785-b3ad-78afd24941a2" />

## List the Top & Bottom 10 Values of a Field

How to list the top 10 values of a field:

	index="_internal"
	| top name

<img width="968" height="615" alt="image" src="https://github.com/user-attachments/assets/c7879803-f46c-4019-8e54-06961f84911a" />

How to list the bottom or last 10 values of a field:

	index="_internal"
	| rare name

<img width="968" height="615" alt="image" src="https://github.com/user-attachments/assets/b41e118b-cbdb-423f-aea1-c0e37a0c1cd3" />

## Dashboards

[Dashboards](https://help.splunk.com/en/splunk-enterprise/get-started/search-tutorial/10.0/part-7-creating-dashboards/about-dashboards) are views that are made up of panels. The panels can contain modules such as search boxes, fields, charts, tables, and lists. Dashboard panels are usually connected to reports. 

A dashboard contains one or more panels. [Dashboard panels](https://help.splunk.com/en/splunk-cloud-platform/create-dashboards-and-reports/simple-xml-dashboards/9.3.2408/build-and-edit-dashboards-in-splunk-web/working-with-dashboard-panels#id_519d4bda_77b8_4b09_a45b_d7c447da85af__Working_with_dashboard_panels) use searches to generate visualizations. Select a panel type depending on the type of search behavior and configuration options that you want. 

Create a **pie chart visualization** that counts the frequency of each **name** field so we can add it to the report:
- Click the **Search** icon to run your search
- Click the **Visualization** tab
- Click the **Chart** button
- Change the visualization to a **pie chart**

	index="_internal"
	| stats count by name

<img width="1211" height="572" alt="image" src="https://github.com/user-attachments/assets/6e779e5c-fcfd-46a6-9566-476b54d4dfc3" />

Save it as a New Dashboard:
- Click **Save As**
- Click **New Dashboard**
- Close the **Selecting a dashboard type** window by clicking **x**

<img width="946" height="575" alt="image" src="https://github.com/user-attachments/assets/404024aa-e9ca-4416-98f3-5f3408674050" />

<img width="643" height="493" alt="image" src="https://github.com/user-attachments/assets/93bafa4a-8d22-48a2-aa33-82e21533c810" />

The difference between Classic Dashboards and Dashboard Studio:
- Classic Dashboard
	- has been developed since Splunk was created
	- has average visualizations that are less interesting than Dashboard Studio's
	- returns data in XML format
	- has a lot of features
- Dashboard Studio
	- very new
	- has the coolest visualizations
	- returns data in JSON format
	- has less features
	- Splunk plans to develop this further and expand its features

Save the panel to your new dashboard using the following settings:
- Click **Save to Dashboard**

<img width="577" height="718" alt="image" src="https://github.com/user-attachments/assets/61391d51-f889-4df6-a48a-9bfe914f0004" />

Click on **View Dashboard**:

<img width="550" height="226" alt="image" src="https://github.com/user-attachments/assets/35c126d9-5ad8-4254-9ab9-80241b735ee1" />

<img width="1117" height="453" alt="image" src="https://github.com/user-attachments/assets/e0a2ec28-b530-4efe-a421-2514c5292a88" />

## Add Panels to Your Dashboard

There are two ways to add panels to your dashboard:
- Within the Dashboard Using the Edit button
- Through Search & Reporting searches

Add panels from the Dashboard Using the Edit button:
- Click **Edit**
- Click **Add Panel**
- Click **New** to expand the chart types
- Click **Area Chart**
- Enter the following Sarch String to make a line chart showing sources from the past hour:

		index="_internal"
		| timechart span=1h count by source

- Click **Add to Dashboard**
- Click ****

<img width="1124" height="155" alt="image" src="https://github.com/user-attachments/assets/d354974a-10c9-4eae-a07b-1941728046de" />

<img width="401" height="132" alt="image" src="https://github.com/user-attachments/assets/6eaad266-6b80-4dab-8dc2-eb3981c6de61" />

<img width="1268" height="360" alt="image" src="https://github.com/user-attachments/assets/d27cd5e5-8bd3-4ac6-83cc-30797a0fc020" />

<img width="956" height="827" alt="image" src="https://github.com/user-attachments/assets/1121d8ff-6681-47b0-ae83-e346ee1c1738" />

Add Panels to Dashboard Using Search & Reporting:
- Click **Apps**
- Click **Search & Reporting**
- Enter the following search in the search bar

		index="_internal"
		| chart count over log_level by host

- Click the **Search** button
- Click **Save As*
- Click **Existing Dashboard**
- Click the **Select an Existing Dashboard** drop-down
- Choose the dashboard that was created earlier
- Click **Save to Dashboard**
- Click **View Dashboard**

<img width="344" height="274" alt="image" src="https://github.com/user-attachments/assets/c3428275-f982-4174-bb04-32bc90b7204e" />

<img width="962" height="547" alt="image" src="https://github.com/user-attachments/assets/3d3f69bd-9de3-41f9-bdfd-6daf216579b3" />

<img width="551" height="504" alt="image" src="https://github.com/user-attachments/assets/611461aa-ebce-43d3-93d3-5c401f68303a" />

<img width="391" height="500" alt="image" src="https://github.com/user-attachments/assets/0f33ed78-7657-47b3-95d4-89cda572ffa7" />

<img width="550" height="226" alt="image" src="https://github.com/user-attachments/assets/dcc06ae7-77aa-4f40-aa13-dfd2a83623d8" />

<img width="964" height="926" alt="image" src="https://github.com/user-attachments/assets/6deefec5-4282-4605-b4a1-ec2b04b91726" />

To resize and move panel(s):
- Click **Edit**
- Move a panel by clicking and dragging it
- Resize a panel by clicking and dragging its side, top, or bottom
- Click **Save**

<img width="957" height="922" alt="image" src="https://github.com/user-attachments/assets/932b17dc-3777-4ff2-9dda-1b7c48e875f7" />

<img width="967" height="157" alt="image" src="https://github.com/user-attachments/assets/65726832-cdff-4076-b323-66376b4f0ddc" />

<img width="982" height="762" alt="image" src="https://github.com/user-attachments/assets/eb095821-edc0-4885-a3d8-0e8334435a41" />

## Splunk Processing Language (SPL) Cheat Sheets
- [Create your own search query](http://gosplunk.com)
- [Splunk cheat sheet](https://www.splunk.com/en_us/blog/learn/splunk-cheat-sheet-query-spl-regex-commands.html)
- [Splunk cheat sheet PDF](https://www.splunk.com/en_us/pdfs/solution-guide/splunk-quick-reference-guide.pdf)

## What I Learned

I learned a lot of things in this project:
- how to search for data using SPL parameters
- how to filter data by date & time and transformation commands
	- by date and time through 
		- the GUI
		- SPL Searches
	- by field
- how to use transformation commands such as
	- stats, used for data aggregation of statistics, similar to SQL aggregation
	- timechart
		- which differs from the chart field by 
			- having one field on the Y axis
			- and another time field on the X axis
	- chart
		- which differs from timechart by having two fields, each on an X and Y axis
- using SPL to list a field's top & bottom 10 values
- how to create dashboards to visualize various search data
- how to add, resize, and move panels that are part of a dashboard
- the difference between Classic Dashboards and Dashboard Studio, mainly
	- development time: 
		- Classic Dashboard was around since the creation of Splunk
		- Dashboard Studio is relatively new in comparison
	- Dashboard Studio having cooler visualizations than Classic Dashboards
	- returned data:
		- Classic Dashboard returns XML data
		- Dashboard Studio returns JSON data
	- Classic Dashboard having more features than Dashboard Studio
	- that Splunk plans to further develop Dashboard Studio and expand its features
