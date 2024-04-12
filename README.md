# SPH-6004-Assignment-2-Team2
**Data Preprocessing**:

*Normalization*: Scale continuous features to a similar range to help the CNN model train more efficiently.

*Data Reshaping*: Although CNNs are typically used for spatial data (e.g., images), we can reshape our time-series data into a 2D format that a CNN can process. Each row (patient's record) can be considered a "channel", similar to how images have RGB channels.

**Feature Selection**:

Given the wide range of features, including lab test results and categorical data, we will initially use all available features. Based on the model's performance, we can later perform feature importance analysis to refine our selection.

**Model Architecture**:

*Input Layer*: Shape the input layer to match the dimensions of our preprocessed data.

*Convolutional Layers*: These will learn spatial hierarchies from the data. We can experiment with different numbers of filters and kernel sizes.

*Pooling Layers*: Use pooling to reduce the dimensions of the data progressively.

*Flatten Layer*: Flatten the output from the convolutional and pooling layers to a 1D vector for the final prediction.

*Dense Layers*: After flattening, use one or more dense layers for prediction.
Output Layer: Since we are predicting a continuous value (time from admission to ICU out time), the output layer should have a single neuron.

**Compilation and Training**:

*Loss Function*: Use Mean Squared Error (MSE) as loss function, since this is a regression problem.

*Optimizer*: Use Adam optimizer.

*Metrics*: Keep tracking the metric Mean Absolute Error (MAE) to monitor performance during training.

**Evaluation and Refinement**:

Depending on the initial results, refine the model by adjusting its architecture, tuning hyperparameters, or revisiting the feature selection process.
