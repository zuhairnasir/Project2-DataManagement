# Airline Performance Analysis (2007)

## Overview

This repository contains an in-depth analysis of **flight cancellations** and **delays** for **airlines in 2007**. The data used in this analysis is extracted from the **airlines2007 dataset**, which includes information on flight schedules, cancellations, delays, and more. The goal of this project is to uncover trends and correlations to help improve airline operations, focusing on factors like **cancellation rates**, **delay patterns**, and **time-based performance**.

The analysis covers various dimensions, including:
- **Flight Delays by Time of Day**
- **Cancellation Reasons**
- **Time Period (Day of the Week, Month)**
- **Problematic Routes**
- **Airline and Airport Performance**

## Data

The dataset used for this analysis includes the following key columns:
- **CRSDepTime**: Scheduled departure time.
- **DepTime**: Actual departure time.
- **ArrDelay**: Arrival delay (in minutes).
- **DepDelay**: Departure delay (in minutes).
- **Cancelled**: Whether the flight was cancelled.
- **CancellationCode**: Code for cancellation reason.
- **UniqueCarrier**: Airline code.
- **Origin, Dest**: Airport codes for origin and destination.

The analysis integrates data from **airports** and **carriers** to provide a comprehensive view of flight performance.

## Key Findings

### 1. **Delay Patterns**
   - **Morning flights** had the **lowest delays**, while **evening flights** experienced the **highest delays** due to air traffic congestion and scheduling issues.
   - **Thursday and Friday** saw the highest cancellation rates, likely due to operational challenges before the weekend.

### 2. **Flight Cancellations**
   - The top reasons for **flight cancellations** were **carrier-related issues**, followed by **weather disruptions** and **air traffic control (NAS) delays**.

### 3. **Time-Based Performance**
   - **Winter months** (December, January, February) saw the highest **cancellation rates**, primarily due to **weather-related disruptions**.
   - **Spring months** (March-May) showed **fewer delays**, with **April and May** performing the best in terms of on-time arrivals and departures.

### 4. **Airline Performance**
   - **Top 5 Airlines** had significantly **higher cancellation rates** compared to other airlines, indicating the need for operational improvements in areas like **maintenance** and **crew management**.

### 5. **Problematic Routes**
   - **LAX to EGE** and **ACK to EWR** were identified as the most **problematic routes**, with the highest **arrival and departure delays**. Operational improvements in **weather management** and **airport congestion** could help reduce these delays.

## Setup and Installation

To get started with the analysis, follow these steps:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/airline-performance-analysis.git
