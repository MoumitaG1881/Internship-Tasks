# Fine-Tune-Model
Fine tune an LSTM based NMT Model\
#Brief Introduction:\
 Neural machine translation (NMT) uses Deep learning (DL) to translate text from one language to another. It is a powerful 
 state-of-art language translation. In this task, a LSTM-based NMT model is built to translate the text from one to another 
 language. Data Source: 'Tab-delimited Bilingual Sentence Pairs' (English to French) from ManyThings.org.\
Steps:\
A. Load Data\
B. Data Preprocessing\
   Process: By converting characters to lowercase, removing punctuation marks, and replacing unicode characters with their 
   ASCII equivalents.\
C. Evaluating the maximum length of both English and French phrases.\
   Significance: This step will determine the lengths of the sequences that will be the input to and output from the model.\
D. Fitting Tokenizer to the phrases and generating padded sequences\
E. Determining vocabulary length\
F. Adding layers
   Brief description:
   * Embedding layer followed by an LSTM layer: To encode English phrases input to the model.
   * RepeatVector layer: To reshape the output from the first LSTM layer that acts as an input to the second LSTM layer.
   * Second LSTM layer: To decode the phrases into their French equivalents (as the task is to translate English to 
     French).
   * Softmax classification layer: It is the final layer that gives probabilities for each word in the French vocabulary.
   * TimeDistributed wrapper: To ensures that the built model provides a set of probabilities for each token (word) in the 
     output.\
     Note: Adam optimizer is used in this task.\
G. Training of the model\
   Description: Here the dataset is split into 80:20 ratio in the training and test sets. Total 50 epochs have been 
   considered with batch size set to 50. Note: If the accuracy fails to improve for five consecutive epochs, the training 
   will be stopped. To implement this, an argument, called 'patience' is set to 5 in 'EarlyStopping' callback.\
H. Training and Validation Accuracy Plot\
   Description: x-axis- Number of Epochs, y-axis- Accuracy\
   Note: This part is not mandatory (if you are not interested in seeing the graphical presentation of training and 
   validation accuracy)\
I. Validating the model\
   Brief Description: Some reserved phrases are used to validate the model.\
J. Test the model: Translation from English to French\
   Note: The model translation task can be tested by putting the sentence (or string of words) of your desire within the 
   single inverted comma.
