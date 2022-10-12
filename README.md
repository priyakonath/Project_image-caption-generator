# Project_image-caption-generator

The project presents a CNN and LSTM-based deep learning approach for caption generation, as well as the GTTS API for text-to-audio conversion.
    - Convolutional Neural Networks are a type of deep neural network that processes data and extracts features from images.
    - Long short term memory (LSTM) is a sort of RNN (recurrent neural network) that will use information from CNN to construct an image description.
    - The gTTS API stands for Google Text to Speech (GTTS). GTTS is a simple to use tool that translates image captions to audio and supports a variety of languages.


## Image Captioning

The process of creating a textual explanation for a set of photos is known as image captioning. Image captioning can be said as an end-to-end Sequence problem, because it turns the image from a series of pixels to a series of words. For this purpose, we need to process both the language or statements and the images. The job of
presenting a summary of the picture is difficult. First it requires understanding the visual information and using natural language processing software to translate the
knowledge into sentences. This includes the creation of a model capable of capturing the association present on the related image in the visual and natural language. Image captioning needs to recognize the important objects, their attributes and how each object is related to each other in an image. It also needs to understand scene type or location, object properties and their interactions. Description sentences must be to generated with proper and correct structure. For that we deal with two types of information, a language one and another image one. While Generating a well-formed sentences it requires both syntactic and semantic understanding of the language.

## Steps involved

   - Dataset Collection
   
     In the project we use Flickr_8K dataset, which contains a image dataset and a text dataset.
      - Flicker8k_Dataset – Image dataset which contains 8091 images.
      - Flickr_8k_text – Dataset which contains text files and captions of images
     
   - Data preprocessing
   
     - Image data preprocessing
        - Resize each image to (299 * 299) Xception model
        - Flatten it 
        - Scaling image pixels (normalization)
     
     - Text data preprocessing
        - Removal of punctuations. 
        -	Removing Words that contain numbers. 
        -	 Removal of single length words. 
        -	Removing special tokens(like ‘%’, ‘$’, ‘#’, etc.) 

   - Feature extraction
   
     This technique is also known as transfer learning since we don't have to do everything
ourselves; instead, we leverage pre-trained models that have already been trained on
big datasets to extract features and use them for our tasks. We're utilising the
Xception model, which was trained on an imagenet dataset with 1000 discrete
classifications to sort through. This model can be easily imported from the
keras.applications folder.

- Creating model 

   CNN-LSTM Model
   Our model consists of 3 main phases
  
    - Image Feature Extraction: Due to the model's efficiency in object detection, the features of the photos are retrieved using the Xception model.
    - Sequence processor: A sequence processor acts as a word embedding layer to handle text input. 
    - Decoder: The model's final phase combines the input from the Image extractor phase and the sequence processor phase and predict caption. 
    
- Training and Testing of model

   We'll use the 6000 photos to train the model by combining the input and
output sequences in batches and fitting them to the model using model.fit_generator()
method and after that we will test the model 
    
- Generating audio 

   gTTS is used for generating audio for image caption 
gTTS (Google Text to Speech) commonly known as the  gTTS API. gTTS is a very easy to use tool which converts the image caption to audio and also it supports several languages.
gTTS supports several languages  including English, Hindi, Tamil, French, German and many more.

  


