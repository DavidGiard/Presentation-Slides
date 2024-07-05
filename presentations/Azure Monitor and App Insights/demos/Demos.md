# Azure Monitor and Application Insights Demos

- Service Health
- Application Insights
  - Create App Insights Service
  - Connect to service
    - App service
    - Virtual Machine
    - Function App
  - Investigate Tools
    - Live Metrics
    - Availability
    - Failures
    - Performance
  - Alerts
  - Diagnostics Settings
  - Dashboard

## Setup

1. Create a web app.
2. Navigate to the web app

## Demo

1. Navigate to [Azure portal](https://portal.azure.com) and log in
2. Search for "Monitor"
3. Left menu: Select [Metrics]
    1. Expand resource groups and resources. Select 1 or more resources (e.g., a web app). Click [Apply]
        1. Select from "Metric" dropdown (e.g., "CPU Time", "Http 4xx")
        2. Show aggregation (e.g., Count, Sum, Min, Max)

## Application Insights Demo

Monitor | Application Insights | Create (~40 seconds)
Create a new Web App (Standard App Service tier)
"Monitoring" tab
    Enable Application Insights
    Select App Insights service you just created

Create Function App
"Monitoring" tab
    Enable Application Insights
    Select App Insights service you just created

Create Virtual Machine
"Monitoring" tab
    Enable Alert rules
    Select App Insights service you just created

## Application Insights SDK for .NET

1. Azure App Insights | Overview blade. Copy:
   - Instrumentation Key
   - Connection String
2. Open ASP.NET MVC application
3. Code added to:
   1. appsettings.json
   2. program.cs
4. HomeController.cs: Show logging code
5. Command:
   1. dotnet add package Microsoft.Extensions.Logging.ApplicationInsights --source https://api.nuget.org/v3/index.json
   2. dotnet run

## Code

### appsetting.json

```json
   
   {
  "ApplicationInsights": {
    "InstrumentationKey": "INSTRUMENTATION_KEY_FROM_AZURE_APP_INSIGHTS_OVERVIEW_BLADE"
  },

```

### program.cs

```C#
dotnet add package Microsoft.Extensions.Logging.ApplicationInsights --source https://api.nuget.org/v3/index.json
```
