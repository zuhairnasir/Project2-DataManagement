# Airline Performance Analysis (2007) ✈️

## 🚀 **Overview**

Welcome to the **Airline Performance Analysis (2007)** project! This repository contains an in-depth analysis of **flight cancellations** and **delays** in 2007. The analysis is based on a dataset that includes **flight schedules**, **cancellations**, and **delays**. The goal of this project is to uncover trends and correlations that can help improve airline operations, focusing on factors like **cancellation rates**, **delay patterns**, and **time-based performance**.

This repository provides the following key analyses:
- **Delay Patterns**: Time of day, day of the week, and month
- **Cancellation Reasons**: Carrier, Weather, NAS, Security
- **Problematic Routes**: Routes with the highest delays and cancellations
- **Airline Performance**: Top 5 airlines vs others

## 🛠️ **Setup and Installation**

### **1. Set Up Virtual Machine (VM)**:
- First, ensure you have a **VM** running with **Ubuntu** or any Linux-based OS. You can use **VirtualBox** or **VMware** for setting up the VM.
- Allocate **sufficient resources** (CPU, RAM, Disk) based on your dataset size and expected workload.

### **2. Install Hadoop on Your VM**:
   - To install **Hadoop**, follow the instructions [here](https://hadoop.apache.org/). You will need **Java** installed for Hadoop to work properly.
   - Install **Hadoop**:
     ```bash
     sudo apt-get update
     sudo apt-get install hadoop
     ```
   - Ensure **Hadoop** is running and correctly configured.

### **3. Install Hive on VM**:
   - Follow the official instructions to set up **Apache Hive** from [here](https://hive.apache.org/).
   - To install **Hive**:
     ```bash
     sudo apt-get install hive
     ```
   - Ensure that **Hive** is integrated with **Hadoop** for data querying.

### **4. Import Data into Hadoop File System (HDFS)**:
   - First, **download** the required **CSV files** from the **Kaggle** webpage.
   - To transfer data from your local machine to the **VM**, use **`pscp`**:
     ```bash
     pscp -P 2222 "C:\path\to\your\data\*.csv" maria_dev@127.0.0.1:/home/maria_dev/zuhair/dm_assignment2/data
     ```
   - **Upload the files to HDFS**:
     ```bash
     hadoop fs -copyFromLocal /home/maria_dev/zuhair/dm_assignment2/data/*.csv /user/maria_dev/zuhair/dm_assignment2/data
     ```

### **5. Load Data into Hive**:
   - After the data is in **HDFS**, you need to create the appropriate **Hive tables** to load the data. For example, create the `airlines2007` table:
     ```sql
     CREATE TABLE airlines2007 (
         FlightDate STRING,
         CRSDepTime INT,
         DepTime INT,
         ArrTime INT,
         CRSArrTime INT,
         UniqueCarrier STRING,
         FlightNum INT,
         TailNum STRING,
         Origin STRING,
         Dest STRING,
         Distance INT,
         Cancelled INT,
         CancellationCode STRING,
         Diverted INT,
         CarrierDelay INT,
         WeatherDelay INT,
         NASDelay INT,
         SecurityDelay INT,
         LateAircraftDelay INT
     ) ROW FORMAT DELIMITED FIELDS TERMINATED BY ',' STORED AS TEXTFILE;
     ```
   - **Load the CSV data into Hive**:
     ```sql
     LOAD DATA INPATH '/user/hive/warehouse/airlines2007.csv' INTO TABLE airlines2007;
     ```

### **6. Install Python Dependencies**:
   Ensure you have the necessary Python libraries for data analysis and visualization. You can install them using the following:
   ```bash
   pip install pandas numpy matplotlib seaborn scipy ipython impyla pmdarima
