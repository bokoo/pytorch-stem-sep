# Wave-U-Net for Music Source Separation

This project implements a Wave-U-Net model for music source separation, enabling the decomposition of a music mixture into separate instrumental stems (e.g., bass, drums, vocals, and others).

The project is intended to explore STEM separation architectures, and the results are of limited quality due to the small dataset (MUSDB18-mini) and limited computational resources as it was trained on free google colab notebook.

## Model Architecture and Training
The model follows a Wave-U-Net architecture, which is based on a convolutional encoder-decoder structure with skip connections. The encoder progressively downsamples the input audio waveform using 1D convolutional layers, while the decoder upsamples the feature maps to reconstruct individual instrumental stems. Skip connections help retain fine-grained details lost during downsampling.

The training process uses the MUSDB18-mini dataset, where each song is split into short 1-second segments. The model is trained using mean squared error (MSE) loss. Adam optimizer is used with learning rate of 0.001.

## Dataset
The model uses the [MUSDB18-mini dataset](https://sigsep.github.io/datasets/musdb.html). Update the `base_path` variable in the script to point to the dataset's location.

### Results and Conclusion
As expected, the limited model size, combined with small training set and suboptimal training due to limited resources lead to unimpressive results compared to state of the art models. Still the model shows some "understanding" and clearly emphasizes the desired instruments especially on Bass and Drums tracks.\
Original mix:\
https://github.com/user-attachments/assets/369fb9f9-f78c-4178-ac34-3f2e1506b3e3\
Drums:\
https://github.com/user-attachments/assets/dad0b39c-ffb8-4131-a3dd-70a1f366a8df\
Bass:\
https://github.com/user-attachments/assets/26b6899d-7be6-4432-8789-7c3daa843af5\
Vocals:\
https://github.com/user-attachments/assets/3c0aab05-5df8-406d-b52e-83abd85e2dd2\
Other:\
https://github.com/user-attachments/assets/5130b2b6-4d85-437b-803c-1965960f93e9\
