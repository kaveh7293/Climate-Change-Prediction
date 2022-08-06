<h1> project description </h1>
<p>	 In this project, I want to estimate what would be the result of the climate change policies to mitigate the consequences of the increase in the atmosphere average temperature. It is believed that carbond dioxide emission is the main reason that the average temperature of the atmosphere increase up to 0.8 C compared to the situation without human-related carbon emission. I collected the data for carbon emission from <a href='https://ourworldindata.org/co2-dataset-sources'> here</a> and data for average atmosphere temeprature from <a href='https://climate.nasa.gov/vital-signs/global-temperature/'>here.</a> The following figures show the carbon dioxide emission and increase in the world temperature in different years. As shown, the increase in world temperature is highly correlated with the CO2 emission:</p><br>
<img src='https://github.com/kaveh7293/Climate-Change-Prediction/blob/main/Carbon_dioxide_emmision.png' width='400' height='300'><br>
<img src='https://github.com/kaveh7293/Climate-Change-Prediction/blob/main/Temp_increase.png' width='400' height='300'><br>
<p> As such, I used a time-series model accounting for CO2 emission as an exogenious variable to predict the temprature increase. In summary, I did the following steps during this project based on the data that I had:
  
  <ol>
    <li> I preprocess the data that I have obtained from two different sources.</li>
    <li> I fit <strong>two different LSTM-based recurrent neural network models </strong> to fit the part of the data chosen for training. </li>
    <li> I compare the results of model predictions for the test data based on different hyperparameter values and model architecture and select the optimal hyperparameter value</li>
    <li> I use the optimal model <strong>to predict what will be the world temperature in 2030 if the Paris agreement goals are met</strong> (i.e., decrease the annual CO2 emission 2 Gt per year).</li> 
  </ol><br><br>
<h3>First LSTM-based RNN Model </h3>


<h3>Second LSTM-based RNN Model </h3>
<p> The architecture of the second type of the RNN model is shown in the following. As shown, with the current model, we use a maxpooling layer to collect the information from all the LSTM layers. By doing so, the model is more capable of accounting for the earlier values in the sequence. <br>
  <img src='https://github.com/kaveh7293/Climate-Change-Prediction/blob/main/First_Model_Architecture.png' width='400' height='600'>

  <table>
  <tr>
    <th> Number of Inputs</th>
    <th>MSE for Test Dataset</th>
  </tr>
  <tr>
    <td>30</td>
    <td>5.09</td>
  
  </tr>
  <tr>
    <td>20</td>
    <td>8.29</td>
  </tr>
  <tr>
    <td><strong>10</strong></td>
    <td><strong>1.23</strong></td>
  </tr>
  <tr>
    <td> 5</td>
    <td>10.15</td>
  </tr>
</table><br>
<p>  The folowing figure shows the predicted values of temperature increase in different years using LSTM-based neural networks compared to the training data:<br><br>
  <img src='https://github.com/kaveh7293/Climate-Change-Prediction/blob/main/Temp_Increase_prediction.png' width='400'  height='300'><br>
  
  The following data also shows the test data set vs. the corresponding predictions for the test data set:<br>
   
<img src='https://github.com/kaveh7293/Climate-Change-Prediction/blob/main/Temp_Increase_prediction_test.png' width='400' height='300'><br>

