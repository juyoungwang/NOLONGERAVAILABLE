# Bike-sharing demand forecasts

This is a toy code I made to do some bike-sharing demand time series forecasting.
To run the code, you should first put your data downloaded from https://www.kaggle.com/competitions/bike-sharing-demand into the data folder of the repository.

I have three neural-network-based time series forecasting methods implemented below:

* A naive LSTM-based one, which has only one LSTM as the intermediate layer. Below is a picture of forecasts I made:
![LSTM result](lstm.png?raw=true "LSTM forecasting picture")

* DeepAR architecture, without ancestral sampling functionality (would require higher amount time to perfectly implement this in Tensorflow). Below is a picture of forecasts I made:
![DeepAR result](deepar.png?raw=true "DeepAR-pseudo forecasting picture")

* DeepAR architecture, with ancestral sampling functionality (perfect version). Below is a picture of forecasts I made:
![DeepARperfect result](deepar.png?raw=true "DeepAR forecasting picture")

My DeepAR implementation differs the other DeepAR tensorflow or pytorch implementaions in the following aspects:
* My implmentation handles categorical features, by applying embedding layers to each of them in a seperate manner.
* After applying embedding, both ordinal and categorical embedded features are concatenated to be used as the input for the LSTM.
* As I used min-max scaler for data, I assumed forecasting value always higher than 0. Because of this reason, I applied "relu" activation for the sake of mean value prediction.
* Sampling-based forecasting functionality is not implemented, due to my limited computational resource (M1 macbook with no GPU). Though, its implementation is quiet straight forward.

As this model is NON-SEQUENTIAL, I had to use custom training loop with state transfer functionality of keras.lstm.

**NOTE**: I have not done any single hyperparameter tunning of the models. These are just implemented for fun, using my M1 macbook, which does not even have CUDA.
