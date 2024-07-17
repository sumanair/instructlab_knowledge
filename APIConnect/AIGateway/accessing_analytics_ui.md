Accessing analytics in the API Manager UI
Last Updated: 2024-06-25
How to view, analyze, and export your analytics data from the API Manager UI.

Analytics data is displayed in dashboards in the API Manager UI. Dashboards are scoped at the provider organization, catalog, and space level.

The ability to access analytics data at a catalog or space level depends on your assigned roles and permissions. For more information about catalogs and spaces, see Working with Catalogs and Using syndication in API Connect.

To access the analytics dashboard, complete the following steps:
In the API Manager UI, select Manage Manage catalogs icon in the navigation panel.
From the list of available catalogs in the API Manager Dashboard, select the required catalog.
If spaces are enabled and want to see analytics at the scope of a space, then:
Click the Spaces tab.
Select the space that you want to view.
Click the Analytics tab.
Analytics dashboards
The analytics dashboards in the API Manager UI show the API event data at the scopes of provider organization, catalog, and space.

The provider organization scoped dashboards are accessed from the analytics icon Analytics icon in the navigation panel.

Catalog scoped dashboards are accessed from the Analytics tab when viewing the catalog:Analytics catalog view

The space scoped dashboards are accessed from the Analytics tab when viewing the space.

The following dashboards are available:
Summary: At a glance information on call volumes, latencies and when those calls are happening.
Consumption: Total API calls in your cloud. Required for consumption-based licensing.
APIs: Everything that you need to know about which APIs are being called and which ones aren't.
Products : Which products are the most popular both in total and over time.
Consumers: Determine which consumer organizations are making the most API calls in total and over time.
Applications: Which applications are responsible for the most API calls both in total and over time.
AI usage: Track AI token counts and model usage to see how AI services are being used.
Status: Critical information on API call successes and failures, showing both success and failure rates over time along with an HTTP response code breakdown.
Latency: How long APIs take to return a response, and the change in latency over time.
Data transfer: All about request and response payloads. Which APIs, consumers and applications are responsible for the largest request and response payloads.
Client information: Who is calling your APIs and from what devices.
Note: Only internet-accessible IP addresses can be resolved to a geographical location. Internal IP addresses are ignored.
Gateway Operations: Call volume and latency information for each gateway in each gateway service. This information can be used to determine whether load is being spread evenly or if a gateway is underperforming.
Each chart in a dashboard can be exported as a PNG or JPG image. The source data for each chart can be exported as a JSON or CSV file. To export a chart, click Actions at the upper right:Analytics example pie chart

It is also possible to enlarge the chart to full-screen by clicking Analytics full screen icon. To see the source data in tabular form click Analytics table icon.

Discover view
By default the Dashboards tab is displayed. To view your API event data in tabular form, select Discover:

Analytics discover viewThe maximum number of API events that can be accessed from the UI is 10,000. The maximum number of event records that can be displayed per page on the Discover view is 200.

You can customize the columns displayed in the Filters section.

You can switch the timeline chart to a logarithmic y axis, and export the data for the chart by clicking Actions at the upper right of the chart:

Export chart data and switch timeline menu

You can export the API event data from the table by clicking Actions at the upper right of the table:

Analytics export chart data menu

Note: When you export from the Discover view, only the data that is displayed on the current page of results is exported. If you want to export the data from all pages, you must export separately from each page. To export all your analytics data, do not use the UI, see Export your analytics data.
If you see unexpected HTTP OPTIONS events in the Discover view, these events are due to CORS requests from browser-based API test tools. For more information about test tools and the OPTIONS call, see Testing an API.

Filtering displayed data
You can filter the data that is displayed in the Dashboards and Discover view by defining filters (also called “queries”). Expand the Filters section to view, define, and apply queries to your displayed data:

Analytics filters settings

You can save and share the queries that you define:
Shared queries are visible to all users at the same scope. They are not visible to users in a different scope. For example, a query that Cloud Manager UI users shares is not visible to an API Manager UI user. Within the API Manager UI, a query that is created at catalog scope is not visible to users who are viewing analytics data at provider organization scope.
Other users cannot edit or delete queries that you share, but they can create a duplicate query, which they can edit and share.
All queries have a name and an optional description. The name does not need to be unique.
Saved queries can be exported as strings for use in REST API and toolkit CLI queries, for example:

Analytics copy query menu optioncopies the following string to the clipboard:
timeframe=last7days

Reports view
The reports view displays long-term summary data rather than individual API events.Analytics reports view
Note: The reports view was introduced in v10.0.6, and does not include data that was generated before upgrade to v10.0.6.
Call volume trends shows your most and least active APIs, total successful and failed API calls, total bytes sent and received, and totals based on scope.Analytics call volume trends tile

Consumer trends shows the number of consumers and subscription and applications counts over time: Analytics consumer trends tile

Inactive products shows products that have no subscriptions, and products that have no traffic.Analytics inactive products tile

Inactive consumer organizations shows consumer organizations that have no applications, subscriptions, recent traffic, or no traffic at all.Analytics inactive consumer organizations tile

Deprecated products shows products that are deprecated but are still receiving traffic.Deprecated products report

The API call volume leaderboards section shows leaderboards for APIs, Products, Plans, Applications, Consumer organizations. Click in the name column to see the data for each item.Analytics call volume leaderboard table

