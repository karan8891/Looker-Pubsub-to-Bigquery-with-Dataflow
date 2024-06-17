1. We are asked to help a newly formed development team with some of their initial work on a new project around real-time driver app data. 
2. We have been asked to assist the team with streaming rides data into BigQuery using Pub/Sub and Dataflow; we receive the following request to complete the following tasks:

    * Create a Cloud Storage bucket as the temporary location for a Dataflow job.
    * Create a BigQuery dataset and table to receive the streaming data.
    * Create up a Pub/Sub topic and test publishing messages to the topic.
    * Create and run a Dataflow job to stream data from a Pub/Sub topic to BigQuery.
    * Run a query to validate streaming data.

3. Some standards we should follow:

    * Ensure that any needed APIs (such as Dataflow) are successfully enabled.


### Task 1. Create a Cloud Storage bucket

* Create a Cloud Storage bucket 

     * gsutil mb gs://bq-bucket


### Task 2. Create a BigQuery dataset and table

* Create a BigQuery dataset called BigQuery dataset name in the region named asia-south2.In the created dataset, create a table called BigQuery table name.


### Task 3. Set up a Pub/Sub topic

* Create a Pub/Sub topic called Pub/Sub topic name. Use the default settings.


### Task 4. Run a Dataflow pipeline to stream data from a Pub/Sub topic to BigQuery

* Create and run a Dataflow job called Dataflow job name to stream data from a Pub/Sub to the BigQuery table we created in a previous task.

* Use the Pub/Sub topic that we created in a previous task: Pub/Sub topic name

* Use the Cloud Storage bucket that we created in a previous task as the temporary location

* Use the BigQuery dataset and table that we created in a previous task as the output table: BigQuery dataset name.BigQuery table name

* Use Region as the regional endpoint.


### Task 5. Publish a test message to the topic and validate data in BigQuery

* Publish a message to your topic using the following code syntax for Message: {"ride_id": "ride001","point_idx": 1,"latitude": 37.7749,"longitude": 122.4194, "timestamp": "2024-06-17T09:30:00Z","meter_reading": 10.5,"meter_increment": 0.3,"ride_status": "ongoing","passenger_count": 2}

* Run a SELECT statement in BigQuery to see the test message populated in your table.

* Note: If you do not see any test messages in your BigQuery table, check that the Dataflow job has a status of Running, and then send another test message.

![project architechture](https://github.com/karan8891/Looker-Pubsub-to-Bigquery-with-Dataflow/blob/main/images/Pubsub2Bq.jpg)
