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
<p>The architecture for the first kind of LSTM-based neural network is shown in the following Figure. As shown, we only use the outputs of the LSTM unit corresponding to the last time step.
  
<img src='https://github.com/kaveh7293/Climate-Change-Prediction/blob/main/Second_Model_Architecture.png' width='550' height='400' ><br>
  We train the RNN model using different sequence lengths for the inputs to find the optimal sequence length. For each model training, I obtained mean squared error of the predictions for the test dataset and divided that by the mean absoloute values of the test dataset to report the percentage of the error. The results are shown in the following table. Note that because the results from model training change from run to run, I trained each model with especfic sequence length four times and reported the avarage value of model accuracy for the test dataset in the table. I will compare the results in the following table with those results that I will obtained when I use a different RNN architecture to decide which architecture is more oppropriate to use. <br>
    <table>
  <tr>
    <th> Number of Inputs</th>
    <th>MSE for Test Dataset</th>
  </tr>
  <tr>
    <td>30</td>
    <td>79.59</td>
  
  </tr>
  <tr>
    <td><strong>20</strong></td>
    <td><strong>16.52</strong></td>
  </tr>
  <tr>
    <td>10</td>
    <td>23.22</td>
  </tr>
  <tr>
    <td> 5</td>
    <td>75.5</td>
  </tr>
</table><br>

</p>
<h3>Second LSTM-based RNN Model </h3>
<p> The architecture of the second type of the RNN model is shown in the following. As shown, with the current model, we use a maxpooling layer to collect the information from all the LSTM layers. By doing so, the model is more capable of accounting for the earlier values in the sequence. <br>
  <img src='https://github.com/kaveh7293/Climate-Change-Prediction/blob/main/First_Model_Architecture.png' width='550' height='400'><br>
  To decide what should be the appropriate dimension of the input sequence, I run LSTM-based estimation using different length for the input sequence and based on higher prediction ability of the model for the test data, I chose the appropriate sequence length. Note that, since the results are stochastic and can vary from run to run, I ran the model fitting step four times and decided based on the average values of the four data. The average values are provided in the following figure.
  
  <table>
  <tr>
    <th> Number of Inputs</th>
    <th>MSE for Test Dataset</th>
  </tr>
  <tr>
    <td>30</td>
    <td>8.92</td>
  
  </tr>
  <tr>
    <td>20</td>
    <td>11.29</td>
  </tr>
  <tr>
    <td><strong>10</strong></td>
    <td><strong>4.93</strong></td>
  </tr>
  <tr>
    <td> 5</td>
    <td>16.8</td>
  </tr>
</table><br>

<p>Comparing the results from two tables showed that the second RNN architecture is better to be used with a sequence length of ten. The folowing figure shows the predicted values of temperature increase using the second architecture with the input length of 10 in different years using LSTM-based neural networks compared to the training data:<br><br>
  <img src='https://github.com/kaveh7293/Climate-Change-Prediction/blob/main/Temp_Increase_prediction_second_case.png' width='400'  height='300'><br>
  
  The following data also shows the test data set vs. the corresponding predictions for the test data set: <br>
   
<img src='https://github.com/kaveh7293/Climate-Change-Prediction/blob/main/download.png' width='400' height='300'><br>

