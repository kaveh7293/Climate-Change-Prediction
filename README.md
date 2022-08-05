<h1> project description </h1>
<p>	 In this project, I want to estimate what would be the result of the climate change policies to mitigate the consequences of the increase in the atmosphere average temperature. It is believed that carbond dioxide emission is the main reason that the average temperature of the atmosphere increase up to 0.8 C compared to the situation without human-related carbon emission. I collected the data for carbon emission from <a href='https://ourworldindata.org/co2-dataset-sources'> here</a> and data for average atmosphere temeprature from <a href='https://climate.nasa.gov/vital-signs/global-temperature/'>here.</a> The following figures show the carbon dioxide emission and increase in the world temperature in different years. As shown, the increase in world temperature is highly correlated with the CO2 emission:</p><br>




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

