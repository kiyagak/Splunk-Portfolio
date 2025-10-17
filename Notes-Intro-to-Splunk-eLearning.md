# Splunk eLearning Course Notes Summary

## Objective

The goal is to list notes taken from the Intro to Splunk eLearning course:
*   Exploring Splunk Web
*   Running searches
*   Using commands
*   Creating reports
*   Creating dashboards
*   Understanding knowledge objects

## What is Splunk?

*   Splunk is a unified data platform that makes machine data accessible and usable across an organization.
*   It helps teams in ITOps, DevOps, and SecOps ensure digital systems are secure and reliable.
*   Splunk's core function is to make machine data available, accessible, and usable.
*   Data is ingested into the index, processed, and made available for searching and analyzing.
*   Queries entered into the search bar find events across multiple data sources, enabling analysis and statistics.
*   Search results can be saved as reports and used to create dashboard panels.
*   Knowledge can be organized into data models for quick visualization and pivoting.
*   Alerts can be set up to notify users of incidents.
*   The example scenario uses Buttercup Games, a fictional gaming company, ingesting data from various sources to solve issues.

## Using Splunk Web

*   The Splunk web interface is accessed after logging into Splunk Enterprise, redirecting to the Splunk Home app.
*   Apps are pre-configured environments extending Splunk's capabilities for specific use cases.
*   User roles (Administrator, Power, User) determine access and permissions.
*   The Home app allows launching apps, managing data, finding documentation, and setting a default dashboard.
*   Splunkbase offers hundreds of apps.
*   The Search & Reporting app provides an interface for searching and analyzing data.
*   Key components of the Search & Reporting app:
    *   Splunk bar: Switch apps, edit account, view messages, manage configuration, monitor search jobs, find help.
    *   App bar: Navigate the application.
    *   Search bar: Run searches.
    *   Time range picker: Retrieve events over a specific time period.
    *   Data summary: Breakdown of data indexed by host, source, and source type.
    *   Table Views: UI-driven data exploration.
    *   Search History: View and rerun past searches.

## Using Search

*   The search bar is used to enter search terms.
*   The Splunk search assistant displays matching terms and syntax documentation.
*   Limiting searches by time is crucial for faster results.
*   Searches become search jobs.
*   The new search page includes:
    *   Save As menu: Save searches as knowledge objects.
    *   Search result tabs (Events, Patterns, Statistics, Visualization).
    *   Search action buttons (Edit, Send to background, Inspect, Delete, Pause, Stop, Share, Print, Export).
    *   Search mode selector (Fast, Smart, Verbose).
    *   Timeline: Visual representation of events over time.
*   Shared search jobs remain active for seven days.
*   Export options: Raw, CSV, XML, or JSON.
*   Search modes:
    *   Fast: Limited field information.
    *   Verbose: Maximum field and event data.
    *   Smart: Toggles behavior based on search type.

## Exploring Events

*   Search results display a list of events in reverse chronological order.
*   The searched text is highlighted in the events.
*   Timestamps are based on the user's time zone setting.
*   Default selected fields: Host, Source, and Source Type.
*   Clicking highlighted text allows adding or excluding the text from the search.
*   The info button displays all extracted fields for an event.

## Using Search Terms

*   Wildcards (e.g., `fail*`) broaden searches.
*   Search terms are not case-sensitive.
*   Booleans (AND, OR, NOT) can be used with multiple terms.
*   Boolean operations have an order of evaluation (NOT, OR, AND).
*   Parentheses control the order of evaluation.
*   Exact phrases can be searched using quotes.
*   Backslashes escape quotes.

## What Are Commands?

*   Splunk's search language consists of search terms, commands, functions, arguments, and clauses.
*   Commands tell Splunk what to do with search results (e.g., create charts, compute statistics).
*   A pipe (|) passes results to the next component.
*   The `search` command filters results at any point in the search pipeline.
*   Command names, clauses, and functions are not case-sensitive, but specific values are.
*   Best practices:
    *   Limit events by time.
    *   Use default fields (index, source, host, source type).
    *   Search for specific terms (e.g., "failed password" instead of "password").
    *   Use inclusion over exclusion.
    *   Use `OR` or `IN` operators instead of wildcards.
    *   Apply filtering commands early.

## What are Knowledge Objects?

*   Knowledge objects help users discover and analyze data.
*   Categories: data interpretation, classification, enrichment, normalization, and search-time mapping (data models).
*   Knowledge objects can be shared, saved, and reused.
*   Knowledge Managers oversee Knowledge Object creation and usage.
*   Types of knowledge objects:
    *   Extracted fields
    *   Calculated fields
    *   Event types
    *   Transactions
    *   Lookups
    *   Workflow actions
    *   Tags
    *   Field aliases
    *   Data models

## Creating Reports

*   Reports save and share searches.
*   Example: A search for failed login attempts is enhanced with geographic context using the `iplocation` command.
*   Quick Reports options: Top values, top values by time, rare values, events with this field.
*   Commands like `top` and `geostats` are used for visualization.
*   Reports are saved with a name, description, and visualization settings.
*   Naming conventions help organize reports.
*   Reports can be accessed from the Reports tab.
*   Report settings include permissions, scheduling, and acceleration.
*   Reports can be scheduled to run at timed intervals and deliver results via email or webhooks.

## Creating Dashboards

*   Dashboards visualize data.
*   Searches returning statistical values can be viewed as charts.
*   Example: Visualizing accounts with login failures using the `top` command and a pie chart.
*   Visualizations can be customized using the format menu.
*   Dashboards are created by saving visualizations to a new or existing dashboard.
*   Dashboard options:
    *   Name and description
    *   Permissions
    *   Classic Dashboards or Dashboard Studio
*   Panels can be added from scratch, from reports, cloned from other dashboards, or pre-built.
*   Dashboards can be visually optimized by moving panels and editing their settings.
*   Drill-down behavior can be configured to make dashboards interactive.

## Dashboard Studio

*   Dashboard Studio is an alternative framework for building dashboards.
*   Dashboards can be cloned from Classic Dashboards to Dashboard Studio.
*   Layout options: Absolute (pixel-perfect) or Grid (automatic alignment).
*   Dashboard Studio features:
    *   Add visualizations, inputs, markdown text.
    *   Configure data sources.
    *   Edit JSON definition.
    *   Customize panel layout by dragging boundaries.
*   Grid Layout is easy to use with limited customization.
*   Absolute Layout offers highly customizable canvas with pixel-perfect control.

## Additional Resources

*   [Splunk Documentation](https://docs.splunk.com/Documentation)
*   [Splunk How-To YouTube Channel](splk.it/How-To)
*   [Splunk Education](https://education.splunk.com)
*   [Splunk Lantern Customer Success Center](https://lantern.splunk.com/)

## Intro to Splunk eLearning Quiz Answers

*   **Which of the following searches will return results containing the terms failed, password, or failed password?**
    *   failed OR password OR "failed password"
*   **Which of the following booleans can be used in a search?**
    *   AND
    *   OR
    *   NOT
*   **When a search is run, in what order are events returned?**
    *   Reverse chronological order
*   **What determines the timestamp shown on returned events in a search?**
    *   The time zone defined in user settings
*   **Which Splunk infrastructure component stores ingested data?**
    *   Index
*   **By default, how long does a search job remain active?**
    *   10 minutes
*   **What are the default roles in Splunk Enterprise?**
    *   Admin
    *   User
    *   Power
*   **Which of the following searches will return results containing the words fail, failure, or failed?**
    *   fail*
*   **By default, which of the following roles are required to share knowledge objects?**
    *   Admin
*   **Which character is used in a search before a command?**
    *   A pipe (|)
*   **By default, who is able to view a saved report?**
    *   The user who created it
*   **What is the most efficient way to limit search results returned?**
    *   time
*   **Which command can be used to further filter results in a search?**
    *   search
*   **Which search mode behaves differently depending on the type of search being run?**
    *   Smart

## What I Learned

- Splunk is a platform that collects and indexes machine data for search, analysis, and visualization.
- It offers a web interface with apps and user roles. 
- Searches use keywords, commands (|), and filters, returning results quickly when limited by time.
- Knowledge objects organize data for reuse.
- Reports and dashboards visualize insights and can be scheduled or customized.
- Dashboard Studio enables easy, flexible dashboard building.
