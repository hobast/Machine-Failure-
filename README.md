# Machine-Failure-
Function preprocesses new input data by converting temperature to Celsius, one-hot encoding categorical variables, scaling features, and uses the trained model to predict failure or no failure.
Here is your `README.md` file content:

```markdown
# Vehicle Failure Prediction Model

This project predicts vehicle component failures based on sensor data using a neural network. It uses various vehicle-related features such as temperature, RPM, fuel consumption, and more to classify whether a failure will occur.

## Installation

To get started with this project, clone the repository and install the required dependencies.

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/vehicle-failure-prediction.git
    cd vehicle-failure-prediction
    ```

2. Install the dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Usage

### Training the Model
To train the model, run the following command:
```python
python train_model.py
```

### Testing the Model
You can test the model by passing new data using the `test_model_usage()` function. Here’s an example:

```python
new_data = {
    'Model': 'Model A',
    'Factory': 'Factory X',
    'Usage': 'High',
    'Membership': 'Gold',
    'Temperature': 77,  # in Fahrenheit
    'RPM': 3500,
    'Fuel consumption': 10
}

result = test_model_usage(new_data)
print(f"Prediction for new data: {result}")
```

## Model Architecture

The model is a neural network with the following structure:

- **Input Layer**: Takes scaled features from the data.
- **Hidden Layer 1**: 64 units, ReLU activation, Dropout (0.3).
- **Hidden Layer 2**: 32 units, ReLU activation, Dropout (0.3).
- **Output Layer**: A single neuron with a sigmoid activation function for binary classification (failure/no failure).

## Data Preprocessing

1. **Temperature Conversion**: Temperatures are converted from Fahrenheit to Celsius.
2. **Handling Missing Values**: Missing categorical values are filled with the most frequent value.
3. **One-Hot Encoding**: Categorical columns are one-hot encoded to convert them into numerical format.
4. **Feature Scaling**: Features are scaled using `StandardScaler` for consistency and better model performance.

## Evaluation

The model is evaluated using the test dataset, and its performance is measured by accuracy. The best-performing model is saved using `ModelCheckpoint` based on validation loss.

## Test the Model

To use the trained model for predictions on new, unseen examples, use the `test_model_usage()` function, which preprocesses the input data and makes a prediction:

```python
new_data = {
    'Model': 'Model B',
    'Factory': 'Factory Y',
    'Usage': 'Low',
    'Membership': 'Silver',
    'Temperature': 85,  # in Fahrenheit
    'RPM': 2000,
    'Fuel consumption': 8
}

result = test_model_usage(new_data)
print(f"Prediction: {result}")
```

## Contributing

Contributions are welcome! Please fork the repository, create a feature branch, and submit a pull request. Ensure that your code adheres to the coding style and passes all tests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```

This `README.md` provides all the necessary information for understanding and using your project, including setup instructions, model architecture, usage examples, and how others can contribute.
