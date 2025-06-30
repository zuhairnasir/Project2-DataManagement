# Airline Performance Analysis (2007) ✈️

## 🚀 **Overview**

Welcome to the **Airline Performance Analysis (2007)** repository! In this project, we perform an in-depth analysis of **flight cancellations** and **delays** using data from **2007**. The analysis includes insights into **delay patterns**, **cancellation reasons**, and **airline performance**. The goal is to identify operational inefficiencies, weather impacts, and patterns that could help airlines optimize performance.

This analysis is based on the **airlines2007 dataset** and includes the following key areas:

- **Delay Patterns** (Time of day, Days of the week, and Months)
- **Cancellation Reasons** (Carrier, Weather, NAS, Security)
- **Problematic Routes** (Routes with the highest delays and cancellations)
- **Airline and Airport Performance** (Top 5 airlines vs Others)

## 📊 **Key Findings**

### **1. Delay Patterns ⏰**
- **Morning flights** 🕖 have the **lowest delays**, with arrival delays averaging 4.18 minutes, and departure delays at 5.36 minutes.
- **Evening flights** 🌆 experience the **highest delays**, with arrival delays averaging 17.40 minutes and departure delays at 18.91 minutes.
- **Thursday and Friday** 📅 see the highest delays, likely due to **increased air traffic** and **weekend operational strain**.

### **2. Flight Cancellations ❌**
- **Carrier delays** 🚁 (internal airline issues) are the most common reason for cancellations (**67,779 flights**), followed by **weather disruptions** 🌧️ (**61,935 cancellations**).
- **NAS-related cancellations** 📡 (air traffic control) and **security concerns** 🔒 are less frequent but still significant.

### **3. Time-Based Performance 🕓**
- **Winter months** ❄️ (**December, January, February**) see the highest cancellation rates, likely due to **weather-related disruptions**.
- **Spring months** 🌸 (**March-May**) and **fall months** 🍂 (**September-November**) show fewer disruptions, with **November** performing the best in terms of on-time flights.

### **4. Airline Performance 🏅**
- **Top 5 Airlines** ✈️ exhibit **significantly higher cancellation rates** compared to other airlines, suggesting the need for operational improvements, particularly in **maintenance** and **crew management**.

### **5. Problematic Routes 🛣️**
- **LAX to EGE** and **ACK to EWR** experience the **highest delays**, primarily due to **weather**, **operational issues**, and **airport congestion**. Improving **weather management**, **airport coordination**, and **flight scheduling** could help reduce delays.

- ## 🛠️ **Setup and Installation**

To get started with the **Airline Performance Analysis**, follow the steps below to set up the **data** and **environment** on your **local VM** and **Hive** database.

### 1. **Set Up Virtual Machine (VM)**:
   - Ensure you have a **VM** running with **Ubuntu** or any **Linux-based OS**. You can use **VirtualBox** or **VMware** to set up the VM.
   - Allocate sufficient resources such as **CPU**, **RAM**, and **Disk** based on your dataset size and expected workload.

### 2. **Install Hadoop on VM**:
   Follow the instructions in the official Hadoop documentation to set up **Apache Hadoop**:
   - Install **Hadoop**:
     ```bash
     sudo apt-get update
     sudo apt-get install hadoop
     ```
   - Configure **Hadoop** and ensure it's working correctly for data storage.

### 3. **Install Hive on VM**:
   - **Download and Install Hive** from [Apache Hive](https://hive.apache.org/).
   - Install **Hive**:
     ```bash
     sudo apt-get install hive
     ```
   - Make sure **Hive** is connected to **Hadoop** for querying the data.

### 4. **Transfer Data to the VM**:
   - Download the necessary **CSV files** from the **Kaggle webpage**.
   - Use **`pscp`** to transfer the CSV files from your **local machine** to the **VM**:
     ```bash
     pscp -P 2222 "C:\path\to\data\*.csv" maria_dev@127.0.0.1:/home/maria_dev/zuhair/dm_assignment2/data
     ```

### 5. **Upload Data to Hadoop File System (HDFS)**:
   - Once the data files are successfully transferred, upload them to **HDFS**:
     ```bash
     hadoop fs -copyFromLocal /home/maria_dev/zuhair/dm_assignment2/data/*.csv /user/maria_dev/zuhair/dm_assignment2/data
     ```

### 6. **Install Python Dependencies**:
   Install the necessary Python packages for **data analysis** and **visualization**:
   ```bash
   pip install pandas numpy matplotlib seaborn scipy ipython impyla pmdarima
