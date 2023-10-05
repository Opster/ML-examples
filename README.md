## Sentiment analysis example
Repository containing all commands to run a sentiment analysis use case, explained on [Opster Blog post](#)

Please note that in this example the file ingestion is automated using filebeat, to parse the file, instead of a manual ingestion using kibana and the sample CSV, with 2k lines is already included.

### Getting Started
```
# 1. Clone this repository
git clone https://github.com/Opster/sentiment-analysis-example

# 2. Enter the sentiment-analysis folder
cd sentiment-analysis

# 3. Run docker-compose build and run commands
docker-compose build
docker-compose up -d
```

### Visualizing Sentiment Data
The data will be available on Elasticsearch after a few minutes, to query the data we can send a request to elasticsearch directly or access kibana ([http://localhost:5601](http://localhost:5601)), query exmaple:
```
curl -XGET "http://localhost:9200/filebeat-*/_search?q=_exists_:review"
```

Please note that before creating visualizations on kibana with the ingested data, first we must [create a data view](https://www.elastic.co/guide/en/kibana/current/data-views.html)
