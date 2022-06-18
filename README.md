# Bike-sharing demand forecasts

This is a toy code I made to do some bike-sharing demand time series forecasting.
To run the code, you should first put your data downloaded from https://www.kaggle.com/competitions/bike-sharing-demand into the data folder of the repository.

I have two neural-network-based time series forecasting methods implemented below:

* A naive LSTM-based one, which has only one LSTM as the intermediate layer. Below is a picture of forecasts I made:
![LSTM result](lstm.png?raw=true "LSTM forecasting picture")

* DeepAR architecture, without ancestral sampling functionality. Below is a picture of forecasts I made:
![DeepAR result](deepar.png?raw=true "LSTM forecasting picture")

**NOTE**: I have not done any single hyperparameter tunning of the models. These are just implemented for fun, using my M1 macbook, which does not even have CUDA.