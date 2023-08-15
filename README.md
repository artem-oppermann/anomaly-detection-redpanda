# Redpanda Anomaly Detection

This repository contains a Python script that demonstrates the use of Kafka for producing and consuming data, specifically sending it to a Redpanda topic, and then using Scikit-learn for anomaly detection. The script generates synthetic data with occasional anomalies and uses an Isolation Forest model to detect these anomalies.

## Prerequisites

* Python 3.x
* Redpanda running on localhost:9092 (or modify the script to point to your Redpanda instance)
* Required Python libraries: kafka-python, numpy, json, scikit-learn
  
You can install the required Python libraries using the following command:

```
pip install kafka-python numpy scikit-learn
```

## How it Works
1. Data Production: The script first produces synthetic data based on a sine wave. Occasionally, it introduces random spikes as anomalies. This data, along with its time-step, is sent to a Redpanda topic named raw-data.
2. Data Consumption: The script then consumes the data from the raw-data Redpanda topic and collects it for training and prediction.
3. Anomaly Detection: Using Scikit-learn's Isolation Forest model, the script detects anomalies in the consumed data.
4. Anomaly Reporting: Detected anomalies, along with their time-steps, are sent to another Redpanda topic named anomalies.
5. Results Display: The detected anomalies and their corresponding time-steps are printed to the console.

#### Usage
1. Ensure Redpanda is running and accessible at localhost:9092.
2. Clone the repository:

```
git clone <repository-url>
```

3. Run the script:
```
python anomaly_detection_with_redpanda.py
```

## Contributing
Feel free to fork this repository, make changes, and submit pull requests. For major changes, please open an issue first to discuss the proposed change.

## License
This project is licensed under the MIT License. See the LICENSE file for details.
