
# Soundtrack Similarity using a Vector Quantization Model

Process of Program Simplified:
  - User Uploads Soundtrack file
  - Uploaded track is run through Librosa functions to extract music features
  - Feature data is run through our Vector Quantization model to find the closest soundtrack in the dataset
  - Display Name of most "similar" soundtrack

# Demo Video of our Application
https://user-images.githubusercontent.com/45269905/206603227-ed158c07-4718-449c-901f-b9187b5947a8.mp4

# System Architecture Diagram
  Displaying the relationship of the system modules from the front-end to the back-end
  ![System Architecture Diagram](https://user-images.githubusercontent.com/113549755/206785473-2c493913-6017-450b-86d0-4d4127c0d50f.png)
  
  
# Model Architecture Diagram
  Displaying the relationship of the model layers from the input layer to the output layer![image](https://user-images.githubusercontent.com/97644172/206308928-1f2f2084-8f80-4801-aae5-bd29debd005b.png)

  
  
  
# Step by Step instructions to train the model to get the trained model weights
The training starts off with defining the VQVAETrainer method in which we take outputs from the VQ-VAE, calculate the losses, backpropagate it, track the losses, and return the results. We take the features of the mfcc file, properly format the file for training, push it through the the VQVAETrainer method, compile it with the proper optimizers, and fit it across our data with 30 epochs. 

# Step-by-step instructions to test the trained model to get the predicted results
We start off the testing of the model by defining the VectorQuantizer class. This class includes the initializing of the embeddings which will be used for quantizing, the call method, and the get_code_indices method. These all come in handy when actually running the model. We then take the trained version of the model and run the .predict method on the testing data. This is followed by the encoders and quantizer running their own layers on the same testing data. First, the encoder will run the same .predict method and turn our data into a feasible way for our quantizer to search through the codebook and return the new output
  
# Directory Guide
VQ_VAE_FINAL.ipynb - Trains, creates, and tests the model.

# Citations or References
  Model architecture diagram: Kumar, Gaurav & Sharma, Sandeep & Malik, Hasmat. (2016). Learning Vector Quantization Neural Network Based External Fault Diagnosis Model for Three Phase Induction Motor Using Current Signature Analysis. Procedia Computer Science. 93. 1010-1016. 10.1016/j.procs.2016.07.304. 
  
 Sayak, P. (2021, July 21). Keras documentation: Vector-quantized variational autoencoders. Keras. Retrieved December 8, 2022, from https://keras.io/examples/generative/vq_vae/  
 
Brownlee, J. (2020) Learning vector quantization for machine learning, MachineLearningMastery.com. Available at: https://machinelearningmastery.com/learning-vector-quantization-for-machine-learning/ (Accessed: December 8, 2022). 


Defferrard, M. et al. (2017) FMA: A dataset for Music Analysis, arXiv.org. Available at: https://arxiv.org/abs/1612.01840 (Accessed: December 8, 2022). 


Larsen, A. et al. (2016) Autoencoding beyond pixels using a learned similarity metric - arxiv, Autoencoding beyond pixels using a learned similarity metric. Available at: https://arxiv.org/pdf/1512.09300 (Accessed: December 8, 2022). 

 








  



