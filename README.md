# Network Traffic Analyzer

A Python-based mini project for analyzing network traffic using the CIC-IDS2017 dataset.

## Objective

The objective of this project is to analyze network-flow data, clean the dataset, identify benign and attack traffic, study important network characteristics, and generate visualizations.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook
- Scikit-learn

## Dataset

CIC-IDS2017 dataset.

Analyzed file:

`Tuesday-WorkingHours.pcap_ISCX.csv`

The dataset is not included in this repository because it is a large dataset file.

## Project Structure

```text
network-traffic-analyzer/
│
├── data/
│   └── Tuesday-WorkingHours.pcap_ISCX.csv
│
├── notebooks/
│   └── log_analysis.ipynb
│
├── results/
│   ├── graphs/
│   └── reports/
│       └── network_traffic_analysis.md
│
├── src/
├── README.md
├── requirements.txt
└── .gitignore

### Data Cleaning
The following steps were performed:
    Removed unnecessary spaces from column names
    Handled missing values
    Removed duplicate records
    Removed records with negative flow duration
    Handled infinite values
    Verified the cleaned dataset

### Final dataset:
    421,828 network flows
    78 features
    412,676 benign flows
    9,152 attack flows

### Attack categories:
    FTP-Patator: 5,933
    SSH-Patator: 3,219

### Analysis Performed
  The project analyzes:
    Benign vs attack traffic
    Attack category distribution
    Flow duration
    Forward and backward packet counts
    Flow bytes per second
    Flow packets per second
    Destination port distribution
    Forward packet-size distribution
    Feature correlations

### Visualizations 
  The following graphs are available in results/graphs/:
    benign_vs_attack.png
    attack_type_distribution.png
    average_flow_duration.png
    average_packet_counts.png
    average_flow_bytes.png
    average_flow_packets.png
    top_10_destination_ports.png
    forward_packet_size_histogram.png
    correlation_heatmap.png

### Dataset Limitation
    The selected CIC-IDS2017 file does not contain a Protocol column. Therefore, destination-port distribution was analyzed instead of protocol distribution.

### Conclusion
    The Network Traffic Analyzer successfully performs data cleaning, statistical analysis, and visualization of network traffic.
    The results provide a foundation for the next stage of the project, where machine learning techniques can be used for network traffic classification.

### Future Work
    The next mini project will focus on applying basic machine learning algorithms to network traffic data.
    The eventual main project will develop an explainable machine-learning-based intrusion detection system.