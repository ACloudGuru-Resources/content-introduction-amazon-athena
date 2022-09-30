# content-introduction-amazon-athena
1194, Introduction to Amazon Athena, Noreen Hasan
Objective #1 - 
* First Query Command: 
CREATE DATABASE real_estate_analytics
* Second Query Command: 
<pre>
CREATE EXTERNAL TABLE IF NOT EXISTS `real_estate_analytics`.`manhattan_sold_houses` (
  `price` double,
  `bedrooms` double,
  `bathrooms` double,
  `sqft` double,
  `status` string,
  `address` string
)
PARTITIONED BY (neighborhood string)
ROW FORMAT SERDE 'org.apache.hadoop.hive.serde2.OpenCSVSerde'
WITH SERDEPROPERTIES (
  'serialization.format' = ',',
  'field.delim' = ',',
  'quoteChar' = '"'
)
LOCATION 's3://nyc-housing-analytics/manhattan-datafeed/'
TBLPROPERTIES ('has_encrypted_data' = 'false', 'skip.header.line.count'='1');
</pre>
