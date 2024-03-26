# Dataset:
- Specifc Dataset:
    - the dataset of the book is being utilised to make the dataset for training the text recognition task, I have used the labelling tool CVAT for acquiring the dataset
    - 3203 images were used for training and 355 images were used for validation
- Generic Datset:
    - IAM words dataset is used to train the text recognition model
    - 86810 images are used for training, 4823 images are used for validation and testing


# Training:

- Firstly to train on the specific dataset I had to spend a lot of time preparing the dataset and clean it(It was a really tiring and nice experience :) , after that I searched for better for working architectures and trained them (the results were good, val acc is around 94%), I had used the pretrained "EAST(Efficient and Accurate Scene Text Detection)" text detection model of OpenCV to detect the text, later feeding those detected text boxes to the text recognition model, an example of the full pipeline is also shown in the notebook . I have used the CTC loss for training the CRNN model and while inferencing I used accuracy as a metric to check the performance of the model

- To train the generic model I had used the famous IAM words dataset, it is composed of handwritten English words extracted from documents, specifically the IAM Handwriting Database, which contains forms of handwritten English text. I used the regular architecture of CRNN with first feww conv2d layers followed by 2 bidirectional LSTM's, and the CTC layer. I have used the CTC loss for training the CRNN model and accuracy as the metric to know the model performance.

### References:
- https://keras.io/examples/vision/captcha_ocr/
- https://github.com/GitYCC/crnn-pytorch
