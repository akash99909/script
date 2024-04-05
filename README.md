SELECT ARRAY_CONCAT(ARRAY[a], ARRAY[b]) AS c
FROM your_table;


SELECT c
FROM (
  SELECT ARRAY_CONCAT(ARRAY[a], ARRAY[b]) AS c
  FROM your_table
)
CROSS JOIN UNNEST(c) AS c;

# script

any HLD for this but couple of major services which are used from GCP are:
Buckets: Buckets will be used for storage of incoming files in excel format. Buckets contain objects which can be accessed with ACL (Access Control List) properties. A bucket is always owned by the associated project's owner.
BigQuery: We will have multiple backend scripts /rule engines for checking and segregating data for utilization in visualization layer from buckets. Following are the checks that will run in BigQuery:
1.	Validation of data that has been added in buckets
2.	Incremental addition of data for specified frequency
3.	Modelling of data for flattening of data, transposing, creating relationships hierarchy and clubbing frequently queried data in parent-child relationships to use nested and repeated fields.
4.	Data is structured and stored a columnar format, with a schema and a data type in every column.
3.	Lastly, Have you considered any other alternatives for hosting this dashboard, such as Workbench?
