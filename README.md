# AVR: Synergizing Foundation Models for Audio-Visual Humor Detection

## Publication

Link to the published Interspeech 2024 Show & Tell Demonstration paper is given here

[Arxiv Link](https://arxiv.org/abs/2406.10448)

You can access the arxiv link and get to know about the following research project.

---

Here is a demostration video submitted to the Interspeech 2024 conference itself that contains the preview of our Tkinter application reviewing any video for its humorous content and predicting whether it is Humorous or Non-Humorous based on certain probabilities.

Video concerned with the following project is presented with this clickable image:


[![Profile Banner](Interspeech_First_Intro_Page.png)](https://drive.google.com/file/d/1szVDejYAwHGkO_e9dLsz2vJ_3nBqrsnj/view?usp=sharing)


---

## Architecture of the System

![Architecture](Architecture_AVR.png)

---

## User Interface of the Tkinter App

- Tkinter App User Interface while uploading a video in this framework
  - We got the buttons to upload the video and check for its predictions (Humor/Non-Humor)

![Profile Banner](Demo_APP.png)

---

## Embeddings Used for this Project

# 1. (VideoMAE + AST) Embeddings

- Using Video Masked Autoencoder, we obtained the embeddings from all the (.mp4) format video files.
- Embeddings shape came out to be of the shape (768,)
-  Audio Spectrogram Transformer Model is used to obtain the embeddings from (.wav) format audio files.
   - Audio embeddings shape came out to be (768,n).
     - where n can be any numerical value based on the variable vector size of audio files.
- Taking the average of those vectors and making it a single vector (768,) helped to feed it to the neural network as shape mismatch wouldn't occur for different audio files.

---

# 2. LanguageBind Embeddings

- LanguageBind has a key ability to obtain embeddings from six different modalities.
- It was experimented apart from the traditional single modality models.
- Much easier to obtain the embeddings from both the audio and video files as compared to our previous models.
- Obtained the embeddings in a matrix form for Audio x Video which was used to feed the model and train on it.
- The model trained on the LanguageBind modality came out to be of less accuracy than our previous approach.
  
---

## Evaluation Scores

Experiment involves testing with two of the most widely used algorithms in Machine Learning:

# 1. Convolutional Neural Network Model

- Feedforwad Neural Network is used with our embeddings from both the cases as discussed above and checked for their performance on both of them.

# 2. LSTM (Long Short Term Memory) Model

- Recurrent Neural Network model is used to subsequently understand that it would be able to comprehend the audio-visual embeddings for the said task.

So, at the end of these experiments we got the following results, as they are mentioned below:

![Results](EvaluationScores.png)
