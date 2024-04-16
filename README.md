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


