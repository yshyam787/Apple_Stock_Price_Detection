Steps in Stock Price Prediction Using LSTM
1. Data Acquisition:
• You fetch historical stock price data using y finance or similar libraries. This includes data such as Open, High, Low, Close prices, Adjusted Close, and Volume.
2. Data Preparation:
• Filtering: You typically focus on a specific attribute, such as 'Close' price, for prediction. Scaling: You scale the data using MinMaxScaler to normalize it between 0 and 1. This helps in improving the convergence of neural networks during training.
3. Creating Training and Testing Sets: Training Data: You create sequences of data (_train) and corresponding target values (y _train) typically using a sliding window approach (in your case, 60 time steps).
• Testing Data: Similarly, you prepare the test data (_test) and the corresponding actual values (y _test) for evaluating the model.
4. Reshaping Data for LSTM: LSTM networks in Keras expect input data to be in a specific format: (samples, time steps, features).
• You reshape _train and _test to fit this format.
5. Building the LSTM Model:
*   You construct an LSTM model using Keras Sequential API.
*   Define the number of LSTM units, layers, and other parameters (Dense layers for output).
1.    Compiling the Model: Configure the model for training using compile (), specifying loss function, optimizer, and metrics.
2.    Training the Model: Fit the model to the training data (*_train, y_train) using fit (). Monitor training progress with metrics like loss and accuracy.
3.    Making Predictions: Use the trained model to predict on x_test. Inverse transform (scaler. inverse_transform ( )) to get predictions in the original scale.
4.    Visualization: Plot the actual stock prices (train[ 'Close ' ]) and the predicted prices (valid[ 'predictions' ]). This helps in visually comparing how well your model predicts against actual data.
