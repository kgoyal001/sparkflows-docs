Datasets
--------

Sparkflows allows you to define your DataSets. These DataSets are then used in Workflows as data sources. DataSet sources can be local file system when running in local mode, or HDFS & HIVE when running on a Spark cluster.



Schema
======
 
  * DataSets have Schema defined for them. This allows Sparkflows to create a Spark DataFrame from them in the workflows.
 
File formats
============
 
  * Sparkflows support various File formats and is able to infer the schema. These include ``CSV/TSV, Parquet, Avro, JSON, XML`` files.
  * Sparkflows also supports creating datasets from ``HIVE`` tables. This is not necessary as in the Workflows HIVE Processors can be directly connected to specific HIVE tables (instead of creating a Dataset in Fire for them).


Dataset Listing Page
====================

The Dataset Listing Page displays all the Datasets created in Fire.

 .. figure:: ../_assets/tutorials/01/dataset-listings.png
   :alt: Dataset Listings
   :align: center
  

 
Create New Datasets
===================
 
You can define a New Dataset by clicking on the ``Create Dataset`` button.


Entering Field Details
^^^^^^^^^^^^^^^^^^^^

Below are the details of the fields in the ``Create Dataset`` page:

- **NAME** : Name of the New Dataset we are creating.
- **DESCRIPTION** : Description of the New Dataset.
- **HAS HEADER ROW** : This is used for CSV/TSV files. It indicates whether the dataset has a header row specifying the name of the columns or not.
- **DELIMITER** : Delimiter field is also used for CSV/TSV files. It indicates the delimiter to be used between the fields in the data.
- **PATH** : Path for the location of the file or directory containing the data files for the Dataset.


 
 .. figure:: ../_assets/tutorials/01/create-new-dataset.png
   :alt: Sparkflows Create New Datasets
   :align: center


Updating the Schema of the Dataset
^^^^^^^^^^^^^^^^^^^^

You can update the Schema of the Dataset by clicking on ``Update``. It would display sample data for the dataset followed by the inferred Schema.

In this case, the data file did not have a header row. So Fire gave it standard column names of ``C0, C1`` etc.

You can update the column names in the schema based on your data.
 
 .. figure:: ../_assets/tutorials/01/dataset-schema.png
   :alt: Dataset Schema
   :align: center
   

Saving the New Dataset
^^^^^^^^^^^^^^^^^^^^

You can click on ``Save`` to save the new Dataset created.
 
 
 
 
 
 
 
 
 
 
 
 




