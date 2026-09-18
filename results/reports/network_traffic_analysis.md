# Network Traffic Analyzer – Analysis Report

## 1. Introduction

This mini project analyzes network traffic using the CIC-IDS2017 dataset. The objective is to understand the characteristics of normal and attack network traffic through data cleaning, statistical analysis, and visualization.

The analysis was performed using Python and Pandas, with Matplotlib used for visualization.

## 2. Dataset

The dataset used for this analysis is the Tuesday Working Hours traffic file from the CIC-IDS2017 dataset.

Dataset file:

`Tuesday-WorkingHours.pcap_ISCX.csv`

After cleaning, the dataset contained:

- Total network flows: 421,828
- Features: 78
- Target column: Label
- Benign traffic: 412,676
- Attack traffic: 9,152

The attack traffic consisted of:

- FTP-Patator: 5,933
- SSH-Patator: 3,219

## 3. Data Cleaning

The following preprocessing steps were performed:

1. Column names were stripped of unnecessary spaces.
2. Missing values in `Flow Bytes/s` were handled.
3. Duplicate records were removed.
4. Records with negative `Flow Duration` were removed.
5. Infinite values in `Flow Bytes/s` and `Flow Packets/s` were replaced and handled using median values.
6. The cleaned dataset was verified to contain no missing or infinite numerical values.

The final dataset contained 421,828 valid network-flow records.

## 4. Traffic Analysis

The analysis compared benign traffic with attack traffic and examined the distribution of the two attack categories.

The dataset was highly dominated by benign traffic, while FTP-Patator and SSH-Patator represented a smaller portion of the network flows.

Different network characteristics were also compared, including:

- Flow duration
- Forward and backward packet counts
- Flow bytes per second
- Flow packets per second
- Destination ports
- Forward packet sizes

## 5. Visualization Results

The following visualizations were generated:

1. Benign vs Attack Traffic
2. Attack Type Distribution
3. Average Flow Duration by Traffic Type
4. Average Packet Counts by Traffic Type
5. Average Flow Bytes per Second
6. Average Flow Packets per Second
7. Top 10 Destination Ports
8. Forward Packet Size Distribution
9. Correlation Heatmap

The dataset did not contain a `Protocol` column. Therefore, instead of creating a protocol distribution that could not be supported by the available data, destination-port distribution was analyzed.

## 6. Important Findings

The analysis produced several observations.

### Traffic Distribution

Benign traffic was much more common than attack traffic in the selected dataset. This demonstrates the class imbalance present in the data.

### Attack Categories

FTP-Patator had more records than SSH-Patator in the analyzed Tuesday traffic.

### Flow Duration

Flow duration varied between the traffic categories. This feature may provide useful information for distinguishing different types of network activity.

### Packet Counts

SSH-Patator traffic showed higher average forward and backward packet counts than the other analyzed categories.

### Flow Rates

The average flow bytes per second and flow packets per second differed between traffic categories, showing that traffic rate characteristics can be useful for network traffic analysis.

### Destination Ports

Ports such as 53, 443, and 80 were among the most frequently observed destination ports in the dataset.

### Correlation

The correlation analysis showed very strong relationships among some packet-count and packet-length features. For example, `Total Fwd Packets` and `Total Backward Packets` had a correlation of approximately 1.00 in this dataset.

`Flow Bytes/s` and `Flow Packets/s` showed a correlation of approximately 0.27.

Most other selected feature relationships were relatively weak.

## 7. Conclusion

The Network Traffic Analyzer successfully cleaned and analyzed network-flow data from CIC-IDS2017. Statistical analysis and visualizations helped identify differences between benign and attack traffic and provided an understanding of important network features.

This project provides a foundation for the next stage of the work, where machine learning techniques can be applied to classify network traffic and detect attack categories.

## 8. Limitations

The analysis was performed on one selected CIC-IDS2017 traffic file rather than the complete dataset.

The selected file did not contain a Protocol column, so destination-port analysis was used instead for protocol-related traffic exploration.

The project focused on exploratory data analysis and visualization. No machine-learning classification model was trained as part of this mini project.