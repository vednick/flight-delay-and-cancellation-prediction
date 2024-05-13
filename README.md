# Flight Delay and Cancellation Prediction

## Short description
This project focuses on predicting flight delays and cancellations originating from Washington DC, using machine learning techniques.

## Proposed Development Platforms
Databricks is used as a Big Data Platform. The dataset is uploaded to Databricks DBFS for filtering and selecting only flights from Washington DC. Then, the exploratory analysis is made by PySpark. Machine Learning models are built using Spark MLlib.

## Dataset
Dataset source: https://www.kaggle.com/datasets/patrickzel/flight-delay-and-cancellation-dataset-2019-2023

This is an extensive dataset with flight information from 2019 to 2023, so we have information about flights before COVID-19, during the pandemic, and after it.

**To download the dataset:**
- Find section "Data Explorer" on the right side.

![image](https://github.com/vednick/flight-delay-and-cancellation-prediction/assets/89455576/c8a15ff2-2189-4481-ba11-81703f97e399)

- Click on the text "flights_sample_3m.csv". The information about the file will appear in the center of the screen with the title "flights_sample_3m.csv(614.14 MB)".

![image](https://github.com/vednick/flight-delay-and-cancellation-prediction/assets/89455576/21d40c04-3d6a-4f64-b1f0-354be264118d)

- Click on the "download" button (the arrow headed down) and choose the place to save the file "flights_sample_3m.csv.zip". You may need to log in to be able to download the dataset.

![image](https://github.com/vednick/flight-delay-and-cancellation-prediction/assets/89455576/3d2b01fb-1df4-4ed1-a489-201351490e25)

- Extract the file "flights_sample_3m.csv" from the archive.

## Importing the dataset and the notebook to Databricks
- Login to Databricks at https://www.databricks.com/.
- Create a cluster by going to the "Create" tab on the left pane -> Cluster.

![image](https://github.com/vednick/flight-delay-and-cancellation-prediction/assets/89455576/3e9cbbad-5591-4da3-ba03-82d38405c943)

- Name the compute (you can use any name) and select Databricks runtime version. The notebook was created and tested on Runtime 14.3 LTS (Scala 2.12, Spark 3.5.0). Click on the Create compute button.

![image](https://github.com/vednick/flight-delay-and-cancellation-prediction/assets/89455576/43ea6d4b-1139-40ca-a9a2-272b6bbc1267)

- Create a notebook by going to the "Create" tab on the left pane -> Notebook.

![image](https://github.com/vednick/flight-delay-and-cancellation-prediction/assets/89455576/ff8458ff-96d1-4727-b0a0-8c87e026c355)

- Go to File -> Import notebook in the upper left corner.

![image](https://github.com/vednick/flight-delay-and-cancellation-prediction/assets/89455576/0fa539f1-a5dc-421f-9533-e418350d397b)
  
-Upload the notebook file "flights.ipynb".

![image](https://github.com/vednick/flight-delay-and-cancellation-prediction/assets/89455576/7c67a4ad-6bd2-4f9f-86c3-c814dabf9e2f)

- Go to File -> Create table... menu in the upper left corner.

![image](https://github.com/vednick/flight-delay-and-cancellation-prediction/assets/89455576/d449518c-22a8-4a9d-8cb4-9f2c75b93fba)

- Drop the file with the downloaded dataset "flights_sample_3m.csv" to the Files area.
- Click on Create table with UI.
- Select your cluster.
- Click on Preview Table.
- Check the checkbox First row is header.
- Click on Create Table.

## Running the notebook
Use the "Run Cell" button in the upper right corner of every cell.

![image](https://github.com/vednick/flight-delay-and-cancellation-prediction/assets/89455576/a2aeec87-d0c8-497f-a52e-39bad92b9001)

Please don't use the "Run all" button because the code needs more than 1 hour to run, and your cluster will be terminated if you use DataBricks Community Edition.

Please notice that some blocks are commented. These are blocks for cross-validation, and they usually need more than one hour to be executed. We use their results in our models, but do not run them unless you really want it.
Also, there are two blocks of code created to run the code after the cluster termination. You can find them in Cmd 9 and Cmd 10 and run if you need it.
