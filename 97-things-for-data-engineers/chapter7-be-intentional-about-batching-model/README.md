# Be Intentional About the Batching Model in Your Data Pipelines
Before ingesting data in batch, you need to decide how to create batch over time. There are two ways:
1. data_timestamp: the last updated timestamp field in the record.
2. arrival_timestamp: timestamp attached to the record depending on when the record appears to the processing system.

## Data time window (DTW) batching model
A batch is created for a time window when all records with a `data_timestamp` in that window have been received. Use DTW when:

1. Data is extracted from source.
2. Extraction logic can filter on data_timestamp field.

DTW batching is not very predictable since out- of-order records could result in delays.

## Arrival time window (ATW) batching model
It's created at a certain wall-clock time with records that were received in the time window prior to that time. Use this batching when:

1. Records in a batch can be received out of order; i.e., they can have data_timestamps that are outside the arrival time window.
2. Volume of data is very high.

ATW batching is more predictable since batches are created based on wall- clock time without having to wait for all records for a given time window. This predictability allows for more robust resource allocation and tolerance for failures
