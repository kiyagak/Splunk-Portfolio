## Intro to Splunk

### Objective

This [course](https://www.splunk.com/en_us/pdfs/training/intro-to-splunk-course-description.pdf) is for new Splunk users who want to learn how to search, analyze, and visualize data using Splunk’s
Search Processing Language (SPL).

This course will introduce you to Splunk's interface and basic searching techniques, and cover how to create reports,
dashboards, and visualizations. By the end of the course, you will be equipped with the foundational skills to navigate
Splunk, perform basic searches, and continue on your learning journey with our wide offering of educational classes.

#### Module 1 – Intro to Splunk
- **Splunk components**: [Components of a Splunk Enterprise deployment](https://docs.splunk.com/Documentation/Splunk/9.4.1/Capacity/ComponentsofaSplunkEnterprisedeployment)
  - **Splunk indexers** provide data processing and storage for local and remote data and host the primary Splunk data store.
  - A **search head** sends search requests to data-storing indexers and then gathers and shows the combined results. It may or may not store data itself.
  - **Forwarders** are Splunk instances that send data to remote indexers for processing and storage, typically without indexing the data themselves.
  - A Splunk server can act as a **deployment server**, sending updates and settings to other Splunk servers and components like forwarders, indexers, and search heads to keep them all synced.

<img width="500" height="394" alt="image" src="https://github.com/user-attachments/assets/10c615bd-17d9-4555-b9d5-6c941d524747" />

- **Basic Splunk functions**: [Get started with Search](https://docs.splunk.com/Documentation/Splunk/latest/Search/GetstartedwithSearch)

<img width="600" height="588" alt="image" src="https://github.com/user-attachments/assets/6a32d870-f2ee-445f-9da0-11c9bbb014dd" />

#### Module 2 – Using Splunk
- **Define Splunk apps**: [Apps and add-ons](https://docs.splunk.com/Documentation/Splunk/9.3.2/Admin/Whatsanapp)
	- An **app** on Splunk analyzes and visualizes specific data sources using dashboards, searches, and management tools. Some apps need add-ons; they can be free or paid. Store apps locally for best performance.
- **Understand Splunk user roles**, including the pre-defined Splunk Enterprise roles: [About users and roles](https://docs.splunk.com/Documentation/Splunk/9.3.2/Admin/Aboutusersandroles)
	- admin -- this role has the most capabilities assigned to it.
    - power -- this role can edit all shared objects (saved searches, etc) and alerts, tag events, and other similar tasks.
    - user -- this role can create and edit its own saved searches, run searches, edit its own preferences, create and edit event types, and other similar tasks.
    - can_delete -- This role allows the user to delete by keyword. This capability is necessary when using the delete search operator.

- **Search & Reporting app**: [Search and Reporting app](https://docs.splunk.com/Documentation/Splunk/9.3.3/Admin/Thedefaultapps)
- **Splunk Web interface**: [Launch Splunk Web](https://docs.splunk.com/Documentation/SplunkCloud/latest/SearchTutorial/StartSplunk)

#### Module 3 – Using Search
- **Run basic searches**: [Basic searches and search results](https://docs.splunk.com/Documentation/SplunkCloud/9.3.2408/SearchTutorial/Startsearching)
- **Set the time range of a search**: [Select time ranges to apply to your search](https://docs.splunk.com/Documentation/Splunk/9.4.0/Search/Selecttimerangestoapply)
- **Save search results**: [Saving searches](https://docs.splunk.com/Documentation/Splunk/latest/Search/Savingsearches)
- **Identify the contents of search results**: [Search modes](https://docs.splunk.com/Documentation/Splunk/9.0.0/Search/Changethesearchmode)
- **Work with events**: [Splexicon:Event](https://docs.splunk.com/Splexicon:Event)
- **Share search jobs**: [Share jobs and export results](https://docs.splunk.com/Documentation/Splunk/9.4.0/Search/SavingandsharingjobsinSplunkWeb)
- **Export search results**: [Export search results](https://docs.splunk.com/Documentation/Splunk/9.4.2/Search/Exportsearchresults)
- **Select search modes**: [Search modes](https://docs.splunk.com/Documentation/Splunk/9.0.0/Search/Changethesearchmode)
- **Control a search job**: [Search actions](https://docs.splunk.com/Documentation/Splunk/9.0.5/Search/Performsearchactions)

#### Module 4 – Exploring Events
- **Refine searches**: [Anatomy of a search](https://docs.splunk.com/Documentation/Splunk/9.4.2/Search/Aboutsearchlanguagesyntax)
- **Understand timestamps**: [Timestamps and time ranges](https://docs.splunk.com/Documentation/SCS/latest/Search/Timestampsandtimeranges)
- **Use the events tab to add and remove terms from a search**: [Drill down on event details](https://docs.splunk.com/Documentation/Splunk/9.4.0/Search/Drilldownoneventdetails)

#### Module 5 – Search Processing Language
- **Use wildcards to search for multiple terms**: [Wildcards](https://docs.splunk.com/Documentation/Splunk/9.4.2/Search/Wildcards)
- **Understand case sensitivity in searches**: [search](https://docs.splunk.com/Documentation/Splunk/9.4.0/SearchReference/Search)
- **Use booleans to include and exclude search criteria**: [Boolean expressions with logical operators](https://docs.splunk.com/Documentation/Splunk/9.1.0/Search/Booleanexpressions)
- **Use special characters with search terms**: [Wildcards](https://docs.splunk.com/Documentation/Splunk/9.4.2/Search/Wildcards)

#### Module 6 – What are Commands?
- **Understand the anatomy of Splunk's search language**:
  - **Search terms**: [search](https://docs.splunk.com/Documentation/Splunk/9.4.0/SearchReference/Search)
  - **Commands**: [search](https://docs.splunk.com/Documentation/Splunk/9.4.2/SearchReference/Search)
  - **Functions**: [search](https://docs.splunk.com/Documentation/Splunk/9.4.2/SearchReference/Search)
  - **Arguments**: [Understanding SPL syntax](https://docs.splunk.com/Documentation/Splunk/9.3.2/SearchReference/UnderstandingSPLsyntax)
  - **Clauses**: [Understanding SPL syntax](https://docs.splunk.com/Documentation/Splunk/9.4.0/SearchReference/UnderstandingSPLsyntax)
- **Understand best practices for writing searches**: [Write better searches](https://docs.splunk.com/Documentation/Splunk/latest/Search/Writebettersearches)

#### Module 7 – What are Knowledge Objects?
- **Identify the five categories of knowledge objects**:
  - **Data interpretation**: [About fields](https://docs.splunk.com/Documentation/Splunk/9.4.2/Knowledge/Aboutfields)
  - **Data classification**: [About data models](https://docs.splunk.com/Documentation/Splunk/9.4.2/Knowledge/Aboutdatamodels)
  - **Data Enrichment**: [Apps and add-ons](https://docs.splunk.com/Documentation/Splunk/9.3.2/Admin/Whatsanapp)
  - **Data Normalization**: [Investigate knowledge object problems](https://docs.splunk.com/Documentation/Splunk/9.3.1/InheritedDeployment/Searchesandknowledgeobjects)
  - **Data Models**: [About data models](https://docs.splunk.com/Documentation/Splunk/9.4.2/Knowledge/Aboutdatamodels)
- **Understand types of knowledge objects**: [Splexicon:Knowledgeobject](https://docs.splunk.com/Splexicon:Knowledgeobject)

#### Module 8 - Creating Reports and Dashboards
- **Save a search as a report**: [Create and edit reports](https://docs.splunk.com/Documentation/Splunk/latest/Report/Createandeditreports)
- **Edit reports**: [Create and edit reports](https://docs.splunk.com/Documentation/Splunk/9.4.0/Report/Createandeditreports)
- **Use transforming commands to create visualizations**: [About transforming commands and searches](https://docs.splunk.com/Documentation/Splunk/9.4.0/Search/Aboutreportingcommands)
- **Create a dashboard**: [Create a dashboard](https://docs.splunk.com/Documentation/SplunkCloud/latest/Viz/CreateDashboards)
- **Add a report to a dashboard**: [Create and edit reports](https://docs.splunk.com/Documentation/Splunk/latest/Report/Createandeditreports)
- **Edit a dashboard**: [Edit dashboards](https://docs.splunk.com/Documentation/SplunkCloud/latest/Viz/DashboardEditor)

## What I Learned

This course taught me how to find and explore data more easily by running searches with filters and tweaking them to get the info I need. I learned some neat tricks like using wildcards and simple logic (like AND, OR, NOT) to make my searches better. It also showed me how to organize data so it’s easier to understand, plus how to create cool reports and visual charts, and even build dashboards to show everything clearly. Overall, it gave me a solid starting point to dig into data and share what I find in a simple, visual way.
