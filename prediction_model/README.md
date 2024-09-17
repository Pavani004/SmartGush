# Drainage Defect Prediction using Recurrent Neural Networks (RNN)

## **Motivation**
* Analysis of time series data to predict potential defects in drainage systems.
*The project focuses on predicting defective manholes and drainage blockages using a combination of IoT data from sensors and predictive analysis with RNN.
* The goal is to implement a model that predicts drainage issues, allowing timely maintenance and preventing severe flooding.
* The model aims to improve real-time monitoring, fault prediction, and overall maintenance planning for urban infrastructure.
  
## **Requirements** 
* Python (3.6.0)
* Pandas (0.24.1)
* Numpy (1.16.0)
* Keras (2.2.4) 
* Tensorflow (1.13.1)
* Jupyter (4.4.0)
* Matplotlib (3.0.2) and Seaborn (0.9.0)
* Firebase (for sensor data storage and real-time monitoring)

## **Directory Structure**
- __src__:  Contains scripts for machine learning models and RNN implementations.
- __notebooks__: Jupyter notebooks for experimenting with RNN models (LSTM, GRU) optimized for predicting drainage defects.
- __data__:  Contains training data from sensors related to manhole conditions, water levels, and flow rates.

## **Usage** 

* Predicting Drainage Defects with LSTM (Long Short-Term Memory)
```
python3 ./src/LSTM_Drainage.py 
```

* Predicting Drainage Defects with GRU (Gated Recurrent Unit)
```
python3 ./src/GRU_Drainage.py
```

* Example
```
//Running the GRU model with input data from drainage system sensors

python3 ./src/GRU_Drainage.py -i path/to/input_data -p hours_to_predict -e

Options:

-i: Path to sensor data file
-p: Hours for prediction (default: 24)
-e: Include embedded features like weather and time (default: False)

```

## **Updated Summary**

* Both GRU and LSTM models were tested for their effectiveness in predicting drainage defects based on time-series sensor data from the drainage network.
* The Mean Absolute Error (MAE) and Mean Squared Error (MSE) were used as performance metrics.
* Models were trained using drainage-related features like water levels, flow 

# **Methods and Performance**
## Feature Selection:
* Default features include water level, flow rate, and sensor data from manholes.
* Embedded features include day, month, and weather conditions (such as rainfall).
## Model Configuration:
* Models were trained for 20 epochs with 200 steps per epoch, using 0.03 dropouts and recurrent dropouts to avoid overfitting.
## Prediction:
* The model predicts defective manholes or blockages 24 hours in advance, helping the maintenance team to prioritize and address issues before they escalate.
* Performance results:
GRU Model: 0.10 MSE on test dataset
LSTM Model: 0.12 MSE on test dataset



## **Real-time Monitoring and Integration with IoT**
 1.Sensor Data Collection: The IoT system collects real-time data from sensors installed in the drainage network, including water levels and flow rates.
 2.Firebase Integration: Sensor data is stored and processed in Firebase for real-time analysis, allowing the RNN model to predict potential defects dynamically.
 3.Maintenance Alerts: Predictive analysis sends notifications to the maintenance team through the dashboard, preventing issues like manhole blockages or flooding.
 
## **Future Direction**
 ** Expansion of the Model:
- The model can be expanded to include additional sensor data and environmental factors like weather patterns to improve accuracy.
- Integrating live weather data can enhance the predictive capabilities for flood risk in specific areas.
- Further optimization and testing of the RNN models (LSTM and GRU) will continue to refine prediction accuracy.
  
## Disclaimer
This project is currently a work in progress and has not been fully completed. The information provided in this documentation is subject to change as further development and testing are carried out. The author assumes no responsibility or liability for any errors, omissions, or inaccuracies in the current state of the project. The results, methods, and models are experimental and may evolve as the project progresses.
