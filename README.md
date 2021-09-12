# Book-Recommendation-System
### In this project we use three different datasets to come up with a book recommendation system for different users based on how they and others have rated previously purchased books.
#### Tags: Recommendation Systems, Data Science, Machine Learning, Collaborative Filtering

#### Co-created by [Harsh Mudgil](https://github.com/harshmudgil97), [Harshal Pawar](https://github.com/HarshalPawar88), [Saubhagya Verma](https://github.com/saubhagyav) and [Tawheed Yousuf](https://github.com/Tawheed-DS)

#### Links:   
Project presentation: [slideshow](https://docs.google.com/presentation/d/11JheT_KAtUkC3WE4DqWzwdEZxicintxRR4LjkRlJHEg/edit#slide=id.p1)   

Dataset 1: [Users Data](https://drive.google.com/file/d/1-jwfc3lcpaPYdcy8NRAsdq7YbfqWyCAJ/view?usp=sharing) 
Dataset 2: [Ratings Data](https://drive.google.com/file/d/13pjABG9HH2CE_p2pUwYaDOv1i5XoXCXj/view?usp=sharing) 
Dataset 3: [Books Data](https://drive.google.com/file/d/1x3V04b3-Zw3v5jA4LgIZZhx_Q_rNxR7U/view?usp=sharing ) 

![pic readme](https://user-images.githubusercontent.com/85662956/132988335-d51afe7a-581a-44d2-a659-3470705e18a8.png)

### Project Summary:

Recommender systems go hand in hand with the bussinesses that have established their presence on the internet. With the huge amount of products and services available online to customers, it becomes imperative for the bussinesses to boil down the total available items to a select group of items that might be of interest to a customer. This will not only enhance the customer's shopping experience and reduce the efforts which go into making a satisfying purchase but it will also have a tremendous impact on the performance of the bussiness.

In this particular project we were put against three datasets each having a specific information about different aspects that go into a purchase. Users dataset carried information about the customers location and Age. Ratings dataset gave us information about how each customer had rated his/her multiple book purchases on a scale from 1-10 and how a good chunk of customers prefered to act lazy in rating their purchases. These Latter customers' ratings for such purchases were taken to be 0 which stood for an implicit rating in favour of such books.

Our Approach towards this project:

<b>Data cleaning and EDA:</b>

We began our project by performing a primary inspection of all the three datasets. We checked and handled outliers null values and duplicacies in various columns. Once we were assured of a clean set of dataframes we merged them together into a single dataframe to carry our EDA.

Next, we perfomed Exploratory analysis on our dataframe to come up with insights about Authors, Publications, Titles and about different age categories of customers. We also build an interactive dataframe which could provide popularity based recommendation to a new customer and these popularities could be based upon average rating an author, a book, or a publisher had received from previous cutomers.

<b>Model building using KNN:</b>

We then moved on to build a memory based recommender for explicit rating case (1-10) using a Nearest Neighbour approach. Customers who had rated a certain book on good scale would be getting recommendations based on other customers who also had rated that particular book on a good scale.

<b>Model building using SVD:</b>

The next big step was to build a model based collaborative recommender system which could very well be evaluated in realtime. For this purpose we chose a very frequently used model namely Matrix Factorization using SVD. In this approach what we broadly do is set forth a pivot table with Customers and Items as columns and rows, and values for each customer-Item mapping is either a zero or an explicit rating for that particular customer-item pair. This matrix is then decomposed into factors using SVD and the individual element of decomposition is multiplied back into a complete matrix to finally generate recommendations.

<b>Model building for implicit case using KNN:</b>

After we had dealt with the explicit ratings, we started working on implicit ratings case. Firstly, we developed a model based on KNN where in Age of customers was taken as a relevance factor to recommend books. In this recommender, a customer who had previously purchased a certain book, would be recommended books based on other customers' buying patterns who were most nearest to him in terms of age. 

<b>Model building for implicit case using content based approach:</b>

Our dataset lacked any description for the books that there in the data. Our next step was to fetch description of as many books as we could using Google's API. Once we had  successfully fetched the descriptions for a sufficient number of books, we developed a content based model using TFIDF vectorizer. Once this model was built, we could recommend books based on the similarity of content in the books a customer had purchased with the other books that were there in the corpus.

<b>Creating a dummy web page for generating recommendations:</b>

Finally we also developed and tested a web page which could take our models in the backend and produce recommendations to a given input item.
