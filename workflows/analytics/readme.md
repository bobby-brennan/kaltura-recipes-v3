<!--METADATA
{
  "icon": "line-chart",
  "sortOrder": 400,
  "tags": [
    "report"
  ],
  "keywords": [
    "Kaltura Analytics"
  ],
  "summary": "Learn how to retrieve usage statistics from the Kaltura API"
}
-->

# Analytics Reports


## Getting a Top Content report
Find out how your viewers are engaging with your content - which content your viewers are watching the most, and which videos are getting little attention

You must specify a date range for your report. There are two options:
* ```filter.fromDay``` and ```filter.toDay```, which should be specified in YYYYMMDD format
* ```filter.fromDate``` and ```filter.toDate```, which should be in epoch/unix format (i.e. the number of seconds since 1/1/1970)

You should only specify one of the two options.

### API Call
```json
{
  "method": "get",
  "path": "/service/report/action/getTotal",
  "parameters": [
    {
      "name": "reportType",
      "default": "1",
      "hidden": true
    },
    {
      "name": "reportInputFilter[fromDay]"
    },
    {
      "name": "reportInputFilter[toDay]"
    },
    {
      "name": "reportInputFilter[fromDate]"
    },
    {
      "name": "reportInputFilter[toDate]"
    }
  ]
}
```

## Getting other Report Types
You can set reportType to any of the [KalturaReportTypes](https://github.com/kaltura/server/blob/master/alpha/lib/enums/ReportType.php). Set it to TOP_CONTRIBUTORS to Find out who your top contributors are

### API Call
```json
{
  "method": "get",
  "path": "/service/report/action/getTable",
  "parameters": [
    {
      "name": "reportType",
      "default": "5",
      "enum": [
        "1",
        "2",
        "3",
        "4",
        "5",
        "6",
        "7",
        "11",
        "12",
        "13",
        "14",
        "15",
        "16",
        "17",
        "18",
        "201",
        "19",
        "20",
        "21",
        "22",
        "23",
        "24",
        "25"
      ]
    },
    {
      "name": "reportInputFilter[fromDay]"
    },
    {
      "name": "reportInputFilter[toDay]"
    },
    {
      "name": "reportInputFilter[fromDate]"
    },
    {
      "name": "reportInputFilter[toDate]"
    },
    {
      "name": "pager[pageSize]"
    }
  ]
}
```