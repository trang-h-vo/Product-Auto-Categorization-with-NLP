## NLP-Auto-Categorization
In this topic, we'll experiment how Machine Learning can help automate the categorization procedure at an online marketplace, where thousands of new products are listed everyday. Auto-categorization with reasonable accuracy help the company to reduce manual work, speed up the product display & recommendation on the platform, hence boosting sales activities & immprove customer shopping experience.

### Text preprocessing
The text data in French are processed using pos-tags, lemmatization and tokenization with `TfidfVectorizer` and `Keras Tokenizer`. Then, some simple classification models are used to demonstrate the categorization step, evaluate the results & suggest future improvement.

### Modeling
Models used include:
- `SGDClassifier`: accuracy score at 
- `Multilayer Perceptron` with `TensorFlow/Keras`:
    - Settings: 1 hidden layer
    - To prevent overfitting: using a `Dropout` layer and `EarlyStopping`.
    - Hyperparameter tuning using 2 Keras Tuners: `RandomSearch` & `Hyperband`.

### Notebook:
The full Python code can be downloaded from this repo. A browser view is also available here: <a href="https://nbviewer.jupyter.org/github/trang-h-vo/NLP-Auto-Categorization/blob/main/Auto_Categorization.ipynb"> Auto_Categorization.ipynb </a>.

### Dataset
The dataset contains product information as follows:

- `article_id`: Unique id for each item
- `brand`: Item brand
- `provider`: Seller's name
- `title`: Product title
- `description`: Detailed description
- `price`: Item price
- `category_from_provider`: Product category set by seller
- `category_id`: Target category to predict

There are 10,000 instances provided, corresponding to nearly 2,000 product categories. As the number of instances are relatively small compared to the number of classes, the models are likely to underfit and perform poorly. For the demontration purpose, I'll use instances correspond to the 500 most popular categories, accounting for +7,300 rows. In practice, the same steps can be applied to higher number of categories, provided that the available train data is sufficiently large.

#### Disclaimer:
This dataset is provided & used for educational purpose only. 

