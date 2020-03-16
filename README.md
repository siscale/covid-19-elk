## Logstash pipeline 

File: `logstash-pipeline.conf`

Fetches time series data from https://github.com/CSSEGISandData/COVID-19/tree/master/csse_covid_19_data/csse_covid_19_time_series.

The default index name is `covid-19-live-update`. Apply the index template found in `index-template-mapping.json` before starting the pipeline.

## Dashboards, Visuals, Index Pattern (Kibana 7.6.1 only)

File: `kibana-7.6.1-covid-19-dashboard.ndjson`

Index pattern: `covid-19-live-update`

Dashboard title: `COVID 19`

To import, go to `Kibana > Management > Saved Objects`, go to `Import`, select the file then click `Import`.

Warning: trying to import the dashboard into a Kibana version lower than `7.6.1` can lead to unexpected results!

## Watchers

Files: `watcher-with-country.json` and `watcher-with-province.json`

Send email updates about the current situation in a country or region. Import them in `Kibana > Management > Watcher > Create > Create Advanced Watch`, or use the [Watcher API](https://www.elastic.co/guide/en/elasticsearch/reference/current/watcher-api-put-watch.html).

