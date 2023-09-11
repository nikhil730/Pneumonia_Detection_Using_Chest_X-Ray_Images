# Pneumonia Diagnosis in Chest X-ray Images
Dataset

Description: The dataset is organized into 3 folders (train, test, val) and contains subfolders for each image category (Pneumonia/Normal). There are 5,863 X-Ray images (JPEG) and 2 categories (Pneumonia/Normal).

Chest X-ray images (anterior-posterior) were selected from retrospective cohorts of pediatric patients of one to five years old from Guangzhou Women and Children’s Medical Center, Guangzhou. All chest X-ray imaging was performed as part of the patient’s routine clinical care.

A deep learning model was used for the classification, the details of which are given below:

Model

CNN(Convolution Neural Networks)

The CNN consisted of the following layers:
Conv2D layer: Applies 16 filters of size 3x3 to the input images with a ReLU activation function.
BatchNormalization layer: Normalizes the activations of the previous layer.
MaxPooling2D layer: Performs max pooling with a pool size of 2x2, reducing the spatial dimensions by half.
Conv2D layer: Applies 32 filters of size 3x3 with a ReLU activation function.
MaxPooling2D layer: Performs max pooling with a pool size of 2x2.
Conv2D layer: Applies 64 filters of size 3x3 with a ReLU activation function.
MaxPooling2D layer: Performs max pooling with a pool size of 2x2.
Flatten layer: Flattens the output from the previous layer into a 1D vector.
Dense layer: Consists of 512 neurons with a ReLU activation function.
Dense layer: Consists of a single neuron with a sigmoid activation function, representing the output class probabilities.

Additionally, early stopping was used in the model training process to prevent overfitting. The EarlyStopping callback was applied, monitoring the validation loss and stopping the training if the validation loss did not improve for 5 consecutive epochs. This technique helps to avoid overfitting by stopping the training process when the model's performance on the validation data stops improving, thus preventing excessive training that may lead to overfitting. Apart from that, as the data was imbalanced, data augmentation was used to cure the imbalanced dataset.
