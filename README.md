# Machine Learning Project Report - Giselle Halim

## Project Overview
Reading is one of the most useful leisure activities because it can increase knowledge and sharpen thinking skills. Nowadays, interest in reading is becoming increasingly important because of the amount of information that people receive every day. If people lack interest in reading, then they have the potential to leave out important information or fall into the trap of false information. 

According to data from the National Library (Perpusnas) [[1]](https://dataindonesia.id/pendidikan/detail/tingkat-kegemaran-membaca-warga-indonesia-meningkat-pada-2022), the reading habit rate of Indonesian people is 63.9 points in 2022. The score increased by 7.4% compared to the previous year. This is a manifestation of the increasing reading awareness of the Indonesian people. But when viewed from a global perspective, for example ASEAN countries [[2]](https://databoks.katadata.co.id/datapublish/2023/12/08/pisa-2022-kemampuan-membaca-pelajar-indonesia-tergolong-rendah-di-asean), Indonesian young people still have low literacy skills. Out of 8 ASEAN countries, Indonesia occupies the 6th position with a score of 359. This means that Indonesia's literacy skills are at level 1a (can understand short explicit texts and cannot understand long implicit or abstract texts). The data above shows that although public interest in reading has increased, this is not enough when compared to other countries.

There are various reasons for low interest in reading, one of which is that it is difficult to find books that is interesting for a person because some library systems are inadequate. Reading tastes are also not easily recognized by new readers, which discourages them from reading, while the library's ability to recommend reading materials is often limited. 

It is these problems that triggered the attempt to solve them with technology. With machine learning technology, a personalized recommendation system that matches the reader's history and interests can be created. The recommendation system utilizes machine learning technology to analyze and learn patterns from various sides, making it possible to create an accurate recommendation system with a reader, which can even change along with certain personal trends. Nowadays, there are many applications that implement recommendation systems such as music applications, movies, and even online book applications. This shows the importance of recommendation systems in various fields.

In [[3]](https://www.researchgate.net/publication/329392345_Music_Recommendations_Algorithms_Practical_Challenges_and_Applications), several types of recommendations are described, one of which is non-personalized recommendations and only displays a ranking list according to the trend at that time. In the context of this project, it is the trend of books, authors, or genres. There are also those who implement this system by creating curated reading lists such as 'editor's pick' or the like. Then there are non-personalized recommendations but have context, such as specific authors or books. Then there are personalized recommendations but no context. An example is a reading list that is based on reader behavior. Finally, personalized recommendations that are contextual. Recommendations that suggest a reading list by considering current trends with reader behavior.

Recommendation systems can help individuals increase their interest in reading because it will be easier to read books of interest. Hopefully, with the availability of a system that can suggest books that are of interest to readers and increase their reading frequency[[4]](https://ieeexplore.ieee.org/document/9579647). If people's interest in reading increases, this will benefit the country because people are more knowledgeable and can compete internationally.

In addition, recommendation systems are important to implement in libraries (or digital book applications) because of their various benefits for both the reader and the application (or library) itself, namely:
* Improving the reader's experience and satisfaction while reading books because they have the potential to find new books that suit their tastes, or even a 'hidden gem' without having to bother looking for themselves.
* Provide quality book recommendations quickly and precisely according to user characteristics.
* Increase the profit of the app because readers will stay longer with the app and increase their loyalty. 
* Benefit the author because more people will know and read their books thanks to this recommendation system. 

So it cannot be denied that the recommendation system is an important thing in the world of reading and efforts to increase reading interest and literacy skills of the community.

## Business Understanding
**Problem Statements**
How to create an effective book recommendation system with the help of machine learning technology?

There are many books with various authors and genres. This makes readers more prone to feeling overwhelmed by the many choices they have to explore on their own, especially for novice readers who are not familiar with their own tastes. It is time-consuming and ineffective to manually search for new books that suit your taste. Given the low interest in reading and literacy levels in our society, the difficulty in finding a favorite read can be a hindrance to fostering a passion for reading.

In addition, it will be difficult for reading platforms or library staff to suggest books to readers accurately if there is no help from recommendation systems because over time, readers will look for books or reading lists that suit them not just based on trends.

**Goals**
The purpose of this project is to create a book recommendation system that can provide personalized reading lists to readers based on the characteristics of books and the behavior of users with similar tastes. The recommendation system created will utilize machine learning technology. By utilizing machine learning technology, it is expected that readers will have a better experience when reading books on the platform or in the library. The impact does not end there, but also increases reader satisfaction and engagement with the platform or library which can provide more profit and profit for the owner and creator of the work itself.

**Solution Approach**
In accordance with the problems discussed in the problem statement, to create an effective book recommendation system, machine learning technology is needed. This project will focus on creating a recommendation system with machine learning technology. This will be done with a combination of 2 approaches, namely *content based filtering* and *collaborative filtering*.

*Content Based Filtering*

Recommends books that are similar to books that the author has read or liked based on the author-like features of the book. This is useful for readers who already know their tastes or have a favorite author and want to see similar works. Also, it can help readers to be aware of new works by their favorite authors. In addition to old readers, CBF is useful for new readers to find their book tastes by recommending books based on their previous reading. However, the drawback of CBF is that since it is content-based, the recommendations are limited and tend not to be far from their favorite authors or genres.

*Collaborative Filtering*

Recommend books based on the reading behavior of other users with similar tastes. Collaborative filtering provides book recommendations based on reading history, favorite authors, and more from other users with similar behavior. This opens up opportunities for readers to try books that they haven't read because of different authors or genres. The advantage of this approach is that readers can enjoy a wide range of reading types according to the tastes of other similar readers, allowing them to discover new books they like. But since the system relies on other readers' feedback, it takes many readers with diverse tastes to provide effective recommendations. For new readers, it is also potentially less relevant as their behaviors are not yet established.

## Data Understanding
The Book Crossing dataset was collected by Cai-Nicolas Ziegler in August-September 2004 from the Book-Crossing community. This data has been organized and cleaned by Arthur Fortes. The dataset can be accessed at the following link [https://github.com/caserec/Datasets-for-Recommender-Systems/tree/master/Processed%20Datasets/BookCrossing](https://github.com/caserec/Datasets-for-Recommender-Systems/tree/master/Processed%20Datasets/BookCrossing)

This dataset consists of:
 - 272,679 interactions from 2,946 users on 17,384 books.
 - Ratings: 1,295 users and 14,684 books (62,657 ratings given)
 - History: 2,946 users and 17,384 books (272,679 accesses) 
 - Simple demographic info for users (age and domicile)

This dataset is divided into 4 different files with .dat format that the author has converted to .csv format with Microsoft Excel. The files and features are:

**1. book_history** (reader history), each reader has accessed at least 20 books.

        - user
        - item
        - accessed
        
**2. book_ratings** (book ratings from readers)

        - user
        - item
        - ratings (1-10)

**3. users_info** (reader demographic information)

        - User_ID 
        - Location
        - Age

In the users_info data, I tidied up the data by separating the 'location' column into 'city', 'state', and 'country' to facilitate the analysis process. Column separation is done with Microsoft Excel.

**4. items_info** (information about books/items)

        - Book_ID
        - ISBN
        - Book-Title
        - Book-Author
        - Year-Of-Publication
        - Publisher
        - Image-URL-S
        - Image-URL-M
        - Image-URL-L 

### Exploratory Data Analysis
After loading the data and checking the data information, exploratory data analysis was conducted to look deeper into the dataset.

**Readers Demography**

![Bar Chart](https://i.ibb.co/kMHHxjG/city.png)
Figure 1: Cities with the Most Readers

It can be seen in Figure 1 that the city with the most readers is Toronto with more than 30 unique readers.

![Bar Chart](https://i.ibb.co/2y0HSWy/city-2.png)
Figure 2: Cities with the Least Readers

It can be seen in Figure 2 that there are some cities with the least readers such as Aberdare, Abilene, and others that only have 1 reader.

![Bar Chart](https://i.ibb.co/2ccCKwQ/state.png)
Figure 3: State with the Most Readers

It can be seen in Figure 3 that the state with the most readers is California with almost 120 unique readers. This is almost double the number of Texas which holds the second position (around 60 people).

![Bar Chart](https://i.ibb.co/DGc5Z7y/state-2.png)
Figure 4: State with the Least Readers

It can be seen in Figure 4 that there are some states with the fewest readers such as Aragon, Bavaria, and others that only have 1 reader.

![Bar Chart](https://i.ibb.co/CQ81jFQ/country.png)
Figure 5: States with the Most Readers

It can be seen in Figure 5 that the country with the most readers is the USA with over 800 unique readers. This number surpasses other countries such as Canada (second place) which only has less than 200 readers.

![Bar Chart](https://i.ibb.co/qFDH1jt/country-2.png)
Figure 6: Countries with the Most Readers

It can be seen in Figure 6 that there are some countries with the fewest readers such as Belgium, Brazil, and others that only have 1 reader.

![Bar Chart](https://i.ibb.co/nsYFdv9/age.png)
Figure 7: Age Distribution of Readers

From the histogram above (Figure 7), it can be seen that the average age distribution of readers is less than 60 years old with the majority of readers aged between 20 and less than 60 years old.

**Active and Inactive Readers**

![Bar Chart](https://i.ibb.co/XVQPGpQ/active.png)
Figure 8: Readers' Active Status 

In Figure 8, it can be seen that all users/readers in the data are active. Reader status is obtained by seeing if they have a history of reading books in the dataset.

**Readers Who Reads the Most**

![Bar Chart](https://i.ibb.co/cvkC2BM/reader.png)
Figure 9: Readers with the Most Reading History

In Figure 9, we can see the readers who read the most often such as the reader with ID 1186 who has almost 2500 reading history.

**Authors and Their Books**
![Bar Chart](https://i.ibb.co/0QS3NZx/author.png)
Figure 10: Authors with the Most Works in the Dataset

The chart in Figure 10 shows that the author with the most works (or in this context, the most books in the dataset) is Stephen King with more than 100 book titles.

**Publishers and Books They Published**

![Bar Chart](https://i.ibb.co/WzgQtYm/publisher.png)
Figure 11: Publishers that Print the Most Books

Based on the chart in Figure 11, the publisher that prints the most books (or in this context, the most books in the dataset) is Ballantine Books with almost 500 titles.

## Data Preparation
Data preparation is done by performing data cleaning on the user (users_info), ratings (book_ratings), history (book_history), and book (items_info) datasets.

1. Handling missing values in each dataset. Missing value is the loss of one or more data in a column that can cause interference if not properly addressed. In this project, the user dataset has missing values in the city, state, and country columns. No null data is removed because it does not affect the machine learning process (the machine learning process does not use the user dataset). Domicile data will only be used to see reader distribution. In the history dataset, a missing value check is performed which shows that there are no missing values in the dataset. In the ratings dataset, a missing value check is performed which shows that there are no missing values in the dataset. Finally, in the book dataset, a missing value check is performed which shows that there are several missing values. Next, unused columns such as the link column are removed. Then, the missing values are cleaned up to simplify the analysis process.

2. Renaming columns. Changing column names is sometimes important to avoid confusion. In the ratings dataset, the column name 'item' was changed to 'Book_ID' to avoid confusion because the 'item' column actually contains the book ID. 

3. View the statistical distribution of the dataset. The statistical distribution of the dataset can be done with df.describe(), it is important to know the numerical data information in the data such as the presence of outliers. In this project, we look at the statistical distribution of user age. 

4. Removing outliers in the data. Outliers are data that have values outside the normal values in the dataset (the difference is very significant compared to other values). If not addressed, outliers can interfere with the analysis process as they can affect the analysis results with less accurate representations. In stage 2, the statistical distribution of the age data was examined. There was an outlier with a maximum age of 239 years, which is not possible. Therefore, data with age above 100 years was removed because it was potentially an outlier or wrong input. 

Next, features encoding is performed on the data to be used. Features encoding is the process of converting categorical features into numeric because machine learning algorithms can only learn from numeric data. 

The content-based filtering recommendation system uses book information data, and in order for the data to be used in the training process, features encoding must be performed. Features encoding is performed on the book_order dataset because this data is used in content-based filtering.
The techniques performed in features encoding in this project are:
1. Data conversion of each column in the form of a series into a list. 
2. Then, a dictionary is created to determine key-value pairs on Book_ID, Book-Title, and Book-Author data. 

The collaborative filtering recommendation system uses book rating data because the system is based on similar user behavior. In order for the data to be used in the training process, there are several techniques that can be done. The techniques performed in feature encoding in this project are:
1. Perform data encoding on user and Book_ID features. 
2. The results of the encoded data will be mapped to their respective columns.
3. The rating column is converted into float form to facilitate the training process.
4. The data will then be randomized first so that it is not biased (because it is sequential) when training the model. 
5. After randomization, the dataset that will be used for the training process (ratings) is divided into train data and test data with a ratio of 80:20.

## Modeling and Result
**Content-Based Filtering (CBF)**
The content-based filtering recommendation system uses book information data that has been made into a dictionary in the data preparation stage. The system is built using TF-IDF Vectorizer that will find the representation of important features from the book and author data. The array results will be transformed into a matrix form that will show the relationship between the book and its author. Furthermore, cosine similarity is used to find the degree of similarity between books to be recommended. The way this recommendation system works is to recommend several books that have the same author. Users only need to input a book title and they will be able to see books written by the same author. 
The advantages of this method are: 
- Helpful for readers who already know their tastes (e.g., have favorite authors and genres) and want to see similar works.
- Helps readers to be aware of new works by their favorite authors.
- Helpful for new readers to find their book tastes by recommending books based on previous reading (e.g. from the author, or genre). 

The drawback of this method is: 
- CBF is content-based so the recommendations are limited and tend not to be far from their favorite authors or genres.

To test book recommendations with content-based filtering, an example book titled “The Blessing Stone” by Barbara Wood was used. The recommendation model outputs 4 books by Barbara Wood and 1 book by Jill Barnett. The output details can be seen in table 1 below.

| title                | author       |
|----------------------|--------------|
| Virgins of Paradise  | Barbara Wood |
| Perfect Harmony      | Barbara Wood |
| Bajo El Sol de Kenia | Barbara Wood |
| Dreaming             | Barbara Wood |
| Dreaming             | Jill Barnett |

Table 1: Content-Based Filtering Results

**Collaborative Filtering**
For the collaborative filtering recommender system model, the RecommenderNet class was created with the help of the hard model class. In RecommenderNet, the embedding process of user and Book_ID data is performed. Then, dot product multiplication operation is performed, and bias is added for each user and book. The match score is determined on a 0-1 scale with a sigmoid activation function. The model is compiled with binary crossentropy loss, and Adam is used as an optimizer with a learning rate of 0.001. In this project, the training process is only done with 10 epochs because training takes a long time if there are too many epochs.

After the training process, book recommendations will be obtained by searching the list of books that the user has not read. Meanwhile, the rating of books that they have read will be used to recommend similar books that they have never read. The model will make predictions to determine which books are potentially liked by a user. 10 books are predicted to suit the user's taste based on the books given a high rating by the user. 
The advantages of this method are: 
- Readers can enjoy a wide range of reading types according to the similar tastes of other readers, which can allow them to discover new books that they like. 

The drawbacks of this method are: 
- The system relies on other readers' feedback, so it requires a large number of readers with diverse tastes to provide effective recommendations. 
- For new readers, it is also potentially less relevant because their behavior has not yet been established.

In collaborative filtering, the example of user number 432 is used to see the recommendation results from the model. Based on the rating history of user 432, the model recommends books that have received high ratings from other users with similar tastes to user 432. Below, table 2 shows the books that received high ratings from user 432. 

| title                                                                      | author               |
|----------------------------------------------------------------------------|----------------------|
| Walk Two Moons                                                             | Sharon Creech        |
| Wuthering Heights (Wordsworth Classics)                                    | Emily Bronte         |
| This Day All Gods Die: The Gap into Ruin (Gap Series/Stephen R. Donaldson) | Stephen R. Donaldson |
| Visible Heart (Silhouette Romances #275)                                   | Dixie Browning       |
| Heaven's Price                                                             | Sandra Brown         |

Table 2: Books that received high ratings from user 432

Based on the books that user 432 likes, the model provides predictions in the form of book recommendations that might be liked (given a high rating) by user 432. The recommendation results for user 432 can be seen in table 3 below.
| title                                                  | author                    |
|--------------------------------------------------------|---------------------------|
| The Body Farm                                          | Patricia Daniels Cornwell |
| The Secret (Animorphs, No 9)                           | Katherine Applegate       |
| Heir to the Shadows (The Black Jewels Trilogy, Book 2) | Anne Bishop               |
| Si c'est un homme                                      | Primo Levi                |
| The Last of the Wine                                   | Mary Renault              |
| SIVANANDA COMPANION TO YOGA                            | Lucy. Lidell              |
| Blues Lessons: A Novel                                 | Robert Hellenga           |
| The Beaver Papers                                      | Will Jacobs               |
| Understanding Power: The Indispensable Chomsky         | Noam Chomsky              |

Table 3: Book Recommendations for Users 432

## Evaluation
The evaluation metrics used are *root mean squared error* (RMSE) and *loss*. These metrics are used to measure the suitability of the recommendation (prediction) with the actual pattern in the data. Since the recommendation system data is not labeled (has a clear output, such as yes or no), a distance calculation is required.

**Root Mean Squared Error**
This metric is used because the input is numeric (rating) and RMSE can measure the distance between the predicted user rating and the actual rating of similar users. The smaller the RMSE, the better the model. The following is the formula of RMSE.

$$RMSE = \sqrt{\frac{\sum_{i=1}^{n} (y_i - \hat{y_i})^2}{n}}$$

**Loss**
Logarithmic loss or log loss works by penalizing incorrect predictions. Log loss has no upper limit and ranges from 0 to infinity. Log loss closer to 0 indicates higher accuracy, whereas if Log loss moves away from 0 it indicates lower accuracy. In general, minimizing the Log loss provides greater accuracy for the model. The following is the formula for log loss.

$$Log Loss = -\frac{1}{n} \sum_{i=1}^n [y_i \log(\hat{y}_i) + (1 - y_i) \log(1 - \hat{y}_i)]$$

The built model gets a loss score of 0.4955 and 0.1477 for RMSE on training. While in the validation data, the loss score reached 0.5204 and RMSE of 0.1753. The score is not too bad, but it can still be better. One of the triggers for this is the lack of epoch count which is only 10 times considering the length of training time.
Below, you can see a graph of the decrease in loss metrics in the training and validation process in Figure 12.

![Bar Chart](https://i.ibb.co/hD4dvQY/lossmet.png)
Figure 12: Loss Metric Results

In Figure 12, it can be seen that the loss metric shows a significant decrease during training, but the decrease is still very small in validation. Furthermore, in Figure 13, we can see the graph of the decrease in RMSE metrics in the training and validation process.

![Bar Chart](https://i.ibb.co/JcLMHZ1/rmsemet.png)
Figure 13: RMSE Metric Results

Similarly, the RMSE metric in Figure 13 shows a significant decrease during training, but the decrease is still not visible in validation and tends to stagnate given the very small number of epochs.

Based on the results of the above metrics, it can be concluded that the model can solve the problem in the project, namely book recommendations. The loss and RMSE scores show that the recommendations given are quite good and in accordance with the user because they are not too far away from the rating (or taste) of the reader's history.

## References
[[1] DataIndonesia.id (Monavia Ayu Rizaty), “Tingkat Kegemaran Membaca Warga Indonesia Meningkat pada 2022,” dataindonesia.id, Feb. 16, 2023. https://dataindonesia.id/pendidikan/detail/tingkat-kegemaran-membaca-warga-indonesia-meningkat-pada-2022 (accessed Apr. 05, 2024)](https://dataindonesia.id/pendidikan/detail/tingkat-kegemaran-membaca-warga-indonesia-meningkat-pada-2022)
[[2] Databoks (Adi Ahdiat), “PISA 2022: Kemampuan Membaca Pelajar Indonesia Tergolong Rendah di ASEAN | Databoks,” databoks.katadata.co.id, Dec. 08, 2023. https://databoks.katadata.co.id/datapublish/2023/12/08/pisa-2022-kemampuan-membaca-pelajar-indonesia-tergolong-rendah-di-asean (accessed Apr. 06, 2024).](https://databoks.katadata.co.id/datapublish/2023/12/08/pisa-2022-kemampuan-membaca-pelajar-indonesia-tergolong-rendah-di-asean)
[[3] D. Jannach, I. Kamehkhosh, and G. Bonnin, “Music recommendations,” in WORLD SCIENTIFIC eBooks, 2018, pp. 481–518. doi: 10.1142/9789813275355_0015.](https://www.researchgate.net/publication/329392345_Music_Recommendations_Algorithms_Practical_Challenges_and_Applications)
[[4] P. Devika, K. Jyothisree, P. Rahul, S. Arjun, and J. Narayanan, “Book Recommendation System,” 2021 12th International Conference on Computing Communication and Networking Technologies (ICCCNT), Jul. 2021, doi: https://doi.org/10.1109/icccnt51525.2021.9579647.](https://ieeexplore.ieee.org/document/9579647)

