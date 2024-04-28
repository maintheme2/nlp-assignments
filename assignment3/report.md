## NLP, Assignment 3

* Oleg Hlopcev
* o.hlopcev@innopolis.university
* CodaLab nickname: maintheme
* https://github.com/maintheme2/nlp-assignments/tree/main/assignment3

### Solution 1

This approach is based on the [spacy library](https://spacy.io/usage/training).

* F-1 score: 0.38

Firstly, I loaded the library and generated the config via spacy config generator. Next, I created a default pipeline which involves iterating through the training data, creating Doc objects, adding entities to the Doc, and then saving the training data in the required format for spaCy.

Once the training data was prepared and saved in the necessary format, I used the spacy train command to train the NER model based on the configuration specified in the config.cfg file. The model was trained on the training data and evaluated on the same data to determine the best-performing model.

After training and evaluating the models, the best model was loaded using spacy.load("model-best"). Subsequently, the NER model was used to predict entities in the test data. The predictions were stored in a list of NERs, with each entity represented by its start and end character indices along with its label.

Finally, the predicted NERs for the test data were saved in a JSONL file format for further analysis or evaluation. The test data was processed using the loaded NER model, and the predicted entities were added to the test data before saving it in the desired format.