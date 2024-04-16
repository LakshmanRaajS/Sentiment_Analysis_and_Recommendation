# Abstract

In this project, sentiment analysis was performed on a dataset sourced from Amazon Books Reviews - Goodreads-books reviews and descriptions of each book. The dataset comprises feedback from 3 million users on 212,404 unique books. This data is a subset of the Amazon review Dataset, encompassing product reviews and metadata from Amazon, spanning the period from May 1996 to July 2014. The primary objective was to categorize the sentiment of reviews into 'negative', 'neutral', and 'positive' based on the 'review/score' column.

# Datasets

We utilized the "Amazon Books Reviews" dataset for this project. The dataset contains two csv files namely ‘Books_rating.csv’, ‘books_data.csv’ having the following attributes:

1. Books_rating.csv

| S.no | Columns            | Rows  | Datatype | Non-null values |
|------|--------------------|-------|----------|-----------------|
| 1    | Id                 | 3.00m | Object   | 3.00m           |
| 2    | Title              | 3.00m | Object   | 3.00m           |
| 3    | Price              | 3.00m | Float    | 3.00m           |
| 4    | User_id            | 3.00m | Object   | 3.00m           |
| 5    | profileName        | 3.00m | Object   | 3.00m           |
| 6    | review/helpfulness | 3.00m | Object   | 3.00m           |
| 7    | review/score       | 3.00m | Float    | 3.00m           |
| 8    | review/time        | 3.00m | Object   | 3.00m           |
| 9    | review/summary     | 3.00m | Object   | 3.00m           |
| 10   | review/text        | 3.00m | Object   | 3.00m           |

- id: The unique identifier of the book.
- Title: The title of the book.
- Price: The price of the book.
- User_id: The unique identifier of the user who rated the book.
- profileName: The name of the user who rated the book.
- review/helpfulness: Helpfulness rating of the review (e.g., 2/3).
- review/score: Rating ranging from 0 to 5 for the book.
- review/time: Time when the review was given.
- review/summary: The summary of a text review.
- review/text: The full text of the review.

The 'review/score' column was used to determine the sentiment labels: 'negative', 'neutral', and 'positive' for the corresponding reviews in the 'review/text' column.

2. books_data.csv

| S.no | Columns       | Rows   | Datatype | Non-null values |
|------|---------------|--------|----------|-----------------|
| 1    | Title         | 212,404| Object   | 212,403         |
| 2    | description   | 212,404| Object   | 143,962         |
| 3    | authors       | 212,404| Float    | 180,991         |
| 4    | Image         | 212,404| Object   | 160,329         |
| 5    | previewLink   | 212,404| Object   | 188,568         |
| 6    | publisher     | 212,404| Object   | 136,518         |
| 7    | publishedDate | 212,404| Float    | 187,099         |
| 8    | infoLink      | 212,404| Object   | 188,568         |
| 9    | categories    | 212,404| Object   | 171,205         |
| 10   | ratingsCount  | 212,404| Object   | 49,752          |

- Title: The title of the book.
- Description: A brief summary or overview of the book's content and storyline.
- Authors: The names of the authors who wrote the book.
- Image: The URL linking to the book cover image.
- PreviewLink: The link that allows access to a preview or more detailed information about the book on Google Books.
- Publisher: The name of the publishing company responsible for releasing the book.
- PublishedDate: The date when the book was officially published.
- InfoLink: The link that provides additional information about the book on Google Books.
- Categories: The genres or categories to which the book belongs.
- RatingsCount: The total count of ratings received for the book, indicating its popularity or reader feedback.

# Data Characteristics

The dataset consists of feedback from a vast user base on a diverse range of books. With 212,404 unique books and 3 million user reviews, the dataset provides a rich and varied source of information. The 'review/score' column, ranging from 0 to 5, serves as the basis for sentiment categorization. The reviews cover a wide span of time, offering insights into user sentiments over two decades of book reviewing on Amazon. The diversity in book genres, user profiles, and review lengths adds complexity and depth to the analysis of sentiment in this dataset.

# Model Building

## Multinomial Naive Bayes
- Trained using a TF-IDF vectorizer within a pipeline.
- Achieved an accuracy of approximately 81% on the test data.
- Detailed classification report offering insights into precision, recall, and F1-score for each sentiment class.

## K-Nearest Neighbors (KNN)
- Utilized both TF-IDF vectorizer and CountVectorizer (optional) within a pipeline with KNN classifier.
- Attained an accuracy of about 73% on the test data.
- Extracted top features for each class, revealing significant words influencing predictions.

## Gradient Boosting
- Employed a Gradient Boosting Classifier with TF-IDF vectorization in a pipeline.
- Obtained an accuracy of approximately 75% on the test data.
- Analyzed feature importances to identify words crucial for sentiment analysis.

## Logistic Regression
- Trained a Logistic Regression model using TF-IDF vectors.
- Achieved an accuracy of 81% on the test data.
- Comprehensive classification report detailing model performance for each sentiment category.

## Support Vector Machine (SVM)
- Implemented an SVM classifier with a linear kernel using TF-IDF vectors.
- Demonstrated high accuracy, achieving 82% on the test data.
- Generated a detailed classification report highlighting model effectiveness.

## Random Forest
- Employed a Random Forest classifier with TF-IDF vectorization.
- Showcased strong performance with an accuracy of 85% on the test data.
- Provided a comprehensive classification report for each sentiment class.

## XLNet
- Utilized XLNet, a transformer-based model for sentiment analysis.
- Evaluated the model on a validation set, achieving a validation accuracy of 77.06%.
- Conducted a comprehensive analysis of model performance with a focus on accuracy, precision, recall, and F1-score for each sentiment category.

## BERT
- Employed the BERT (Bidirectional Encoder Representations from Transformers) model.
- Achieved a validation accuracy of 75.78%, showcasing the model's effectiveness in capturing sentiment from book reviews.
- Evaluated the BERT model using accuracy as a primary metric, with potential inclusion of precision, recall, and F1-score in a detailed classification report.

## Pearson Correlation
### Key Steps:
1. **User Input:** User provides a set of book titles and corresponding review scores.
2. **Data Processing:** Ratings data is filtered to include users who have reviewed books from the input.
3. **Pearson Correlation Calculation:** Users are grouped based on their book reviews. Pearson Correlation is calculated between the input user and others, indicating similarity in rating patterns.
4. **Top Similar Users Selection:** Users with the highest Pearson Correlation are identified as the top similar users.
5. **Weighted Rating Calculation:** A weighted rating is computed by multiplying the similarity index with each user's review scores.
6. **Recommendation Score Aggregation:** Weighted average recommendation scores are calculated, considering the collective influence of similar users.
7. **Top Recommendations:** Book recommendations are generated by sorting candidates based on their weighted average recommendation scores.

## Enhancing Model Performance Through Advanced Techniques
Explored advanced techniques, employing methods such as Randomized Search Cross-Validation to optimize our models. These techniques are vital for ensuring that our models are not just accurate, but also robust and versatile.

## Random Forest Classifier Optimization
The Random Forest classifier was carefully fine-tuned. Leveraging Randomized Search Cross-Validation, explored a variety of hyperparameters, including the number of estimators, maximum depth, and minimum samples split. Through this process, identified the optimal configuration: 300 estimators, unlimited depth, and a minimum of 2 samples required to split. This meticulous tuning significantly bolstered the model's accuracy and generalizability.

## Naive Bayes Classifier Enhancement
The Naive Bayes classifier, a fundamental algorithm in text classification, was also optimized. By employing Grid Search Cross-Validation, explored different configurations, including term frequency-inverse document frequency (TF-IDF) vectorization parameters and additive smoothing (alpha). The best hyperparameters were determined through this process, enhancing the Naive Bayes model's accuracy and precision.

## K-Nearest Neighbors (KNN) Classifier Refinement
In the case of the KNN classifier, employed a combination of techniques. Utilizing Randomized Search Cross-Validation, explored n-gram ranges and weighting functions, refining the KNN model. By selecting the most appropriate hyperparameters, our KNN classifier exhibited superior performance, accurately capturing complex relationships in the data.

## Gradient Boosting Classifier Optimization
For the Gradient Boosting classifier, applied a systematic approach. Employing Randomized Search Cross-Validation, explored n-gram ranges, the number of boosting stages, learning rates, and maximum tree depths. This detailed exploration led us to the optimal configuration, ensuring that our Gradient Boosting model was finely tuned for accuracy and efficiency.

## Support Vector Machine (SVM) Classifier Enhancement
The SVM classifier, known for its ability to handle complex data, was meticulously fine-tuned. Using Randomized Search Cross-Validation, explored different kernel functions, regularization parameters, and gamma values. The best hyperparameters were selected, empowering our SVM model to accurately classify sentiment in textual data.

## Comprehensive Evaluation and Visualization
In our evaluation process, not only focused on accuracy but also delved into the nuances of precision, recall, and F1-score for each class. Also, visualized the classification report through a heatmap, providing a comprehensive overview of our models' performance across different sentiment classes. This visualization offered valuable insights into the strengths and areas for improvement for each classifier.

### Before Hyperparameter tuning
<img width="519" alt="image" src="https://github.com/SivaranjaniSuresh/Sentiment-Analysis-Amazon-Book-Reviews/assets/114537365/d06be47f-cb7f-416f-8794-01da79a4b713">

### After Hyperparameter tuning 
<img width="519" alt="image" src="https://github.com/SivaranjaniSuresh/Sentiment-Analysis-Amazon-Book-Reviews/assets/114537365/4a9296eb-bab7-41cb-af28-f3ec9df46690">

## Conclusion
Support Vector Machine (SVM) and Multinomial Naive Bayes classifiers emerged as powerful contenders, showcasing an impressive accuracy rate of 89% 
