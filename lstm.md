# Guide to lstm_mods @ Labyrinthine Unreal

# installs

```python3.7.7
Requirements: ...
```
 ### <p>  *Write data to disk to make data machine readable for the model to execute training* </p>

###### 1. summarize.py => read/write data (the most important part of the operation)
     (summarize.py will read data from Fauna Prompts collection and write data to disk.) 
     
###### 2. data.py => an array of sample data
     (add more data to array, the more data the longer the training with the current model shared.)

###### 3. output.txt =>  data from fauna Prompts collection
     (data from Fauna will be stored in this text file.)
     

<br> <br>
 ### <p>  *LSTM MODs interactions* </p>

###### 1. app.py => python Fauna api
     (python app.py will fetch data from Unity C# scripts JSON payload and post data to Fauna.)
     

###### 2. automateTask.py => ChatGPT conversation modelling
     (automateTask.py will generate randomized conversations via the OpenAI chatGPT api. )
     (The randomized conversations generated will be joined in the Prompts collection on Fauna. )


###### 3. diralect.py => diralect.py
     (diralect.py will gather Prompts data from Fauna and perform Latent Diraclect Allocation as well as Topic Modelling)
     (Latent Dirichlet Allocation (LDA) is an algorithm that can be used to build models that can quickly identify the key topics in a text corpus, allowing for easy generalization to any new text corpus.)
     (Preprocessing for Topic Modelling Topic Modelling is an approach for finding topics in large amounts of text.)
     (Topic modeling is great for document clustering, information retrieval from unstructured text, and feature selection.)
     
     
###### 4. eval.py> Standalone AI model for frontend stack like ChatGPT.
     (performs inference utilizing the saved Keras model. This model can be used on frontend or command line.)

<br> <br>

     
 ### <p>  *Training* </p>

###### 1. process.py => Training the model
     (Long Short Term Memory network)
     (process.py freezes the state of a TensorFlow session into a pruned computation graph. It removes unnecessary subgraphs, device directives, and variables to create a graph that is more portable and efficient. It can also convert variables to constants and save the frozen graph definition.)
     ( This Keras model is designed to tokenize text data, convert it to sequences, and then use an embedding layer, two LSTM layers, and a dense layer to create a model that can predict the next sequence of words.)
     (The model is trained using a sparse categorical cross-entropy loss and an Adam optimizer, and the model is saved to a file after training.)
     (The model is designed to be able to predict the next sequence of words in a text data set.)
<br><br>
     

###### 2. torch_lstm.py => Conversion
     (copy/pasta of the Keras LSTM model from process.py) 
     (exports LSTM model as ONNX model to be machine readable in unity) 









