# Apache Beam Example

## Compile & Package

```
mvn clean package
```

## Environment Variables

```
export GOOGLE_APPLICATION_CREDENTIALS=path/to/my/credentials.json
export BUCKET_NAME=BUCKET
export PROJECT_NAME=PROJECT
export DATASET_ID=DATASET
export TABLE_ID=TABLE
```

## Run
```
mvn compile exec:java -Dexec.mainClass=PubSubToBigQuery -Dexec.cleanupDaemonThreads=false -Dexec.args="--project=$PROJECT_NAME --inputTopic=projects/$PROJECT_NAME/topics/my-topic --output=gs://$BUCKET_NAME/output --runner=DataflowRunner --windowSize=2 --projectId=$PROJECT_NAME --datasetId=$DATASET_ID --tableId=$TABLE_ID "
```
##