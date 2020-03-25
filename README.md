## Logstash pipeline 

The default index name is `covid-19-live-update`. Apply the index template found in `index-template-mapping.json` before starting the pipeline.

Choose one pipeline from the following:

# Using daily reporting data

File: `logstash-github-covid-19-daily-reports-template.conf`

Fetches time series data from https://github.com/CSSEGISandData/COVID-19/tree/master/csse_covid_19_data/csse_covid_19_daily_reports.

This dataset contains county-level reporting for some countries, including US.

# Using global time series data

File: `logstash-github-covid-19-time-series-template.conf`

Fetches time series data from https://github.com/CSSEGISandData/COVID-19/tree/master/csse_covid_19_data/csse_covid_19_time_series.

This is the original pipeline that was deprecated in favor of the daily reports data.

This time series data is less granular the that daily reporting data, and doesn't contain county data. We recommend using the daily reports pipeline instead.

## Dashboards, Visuals, Index Pattern (Kibana 7.6.1 only)

File: `kibana-7.6.1-covid-19-dashboard.ndjson`

Index pattern: `covid-19-live-update`

Dashboard title: `COVID 19`

To import, go to `Kibana > Management > Saved Objects`, go to `Import`, select the file then click `Import`.

Warning: trying to import the dashboard into a Kibana version lower than `7.6.1` can lead to unexpected results!

## Watchers

Files: `watcher-with-country.json` and `watcher-with-province.json`

Send email updates about the current situation in a country or region. Import them in `Kibana > Management > Watcher > Create > Create Advanced Watch`, or use the [Watcher API](https://www.elastic.co/guide/en/elasticsearch/reference/current/watcher-api-put-watch.html).
