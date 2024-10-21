# Research of LSTM for forecasting meteorological weather data
The problem was to investigate the possibility of using neural networks for weather forecasting. LSTM was implemented using the TensorFlow framework and the Pandas, Keras, and SKlearn libraries in the Python, as well as a comparative analysis of meteorological data forecasting methods. 
The forecast using this model reaches an accuracy of up to 90% for a number of meteorological parameters. The neural network has shown that it is able to search for periodicity in data and at the same time is able to predict the seasonal trend.

For more details with examples, see [Documentation.](https://github.com/YuliaKUA/WeatherForecast/blob/main/lstm-wp_last_3.ipynb)

The peculiarity of this study is the choice of the neural network architecture, the creation of a training set as a set of meteorological data for 10 years from more than 100 weather stations, as well as a prediction interval of 7 days in the future. 
 
## The research considers 2 approaches to creating a forecast: 
### Getting the predicted values at a certain coordinate by interpolating the forecast for 4 weather stations.
The model is trained on data from one weather station, then a forecast is made at 4 points using meteorological data from these coordinates, and then values for an arbitrary point are found using interpolation. 
 
<img src="https://github.com/YuliaKUA/WeatherForecast/blob/main/src/2.png">
 
### Getting the predicted values at a certain coordinate immediately after training the model on a specially generated dataset.
In this case, the training data set is formed as follows, data is collected from 10 (or more) weather stations in one area, an arbitrary coordinate in this area is selected and a set of meteorological data is formed at this point using interpolation, so it is repeated for 10 areas. The final set of training data consists of a set of meteorological parameters of these 10 points. The model is trained on this resulting data set and then we use it to make a forecast at an arbitrary point (taking into account that the data for the forecast at this coordinate is prepared in advance or an existing archive is used, for example, from a weather station). 

<img src="https://github.com/YuliaKUA/WeatherForecast/blob/main/src/1.png">
