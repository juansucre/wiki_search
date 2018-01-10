# Semantic Search

## The Task
The objective of this project was to engineer a novel wikipedia search engine that takes in a search query and returns the top relevant Wikipedia articles using natural language processing. The search engine is limited to articles under the Machine Learning and Business Software categories.


### Method
The process was divided into two main steps:
1. Collection
1. Search

### Collection
The first step of this project involved collecting all of the information from all articles under the Machine Learning(ML) and Business Software (BS) categories. I used the Wikipedia API to pull all the articles under those categories as well as the articles from their respective subcategories. The article information included `page_id`, `title` and `text`.

The raw page text and its category information was written to a collection on a Mongo server running on a dedicated AWS instance.

### Search
With the page information stored in a Mongo server, this step consisted of three basic subsequent steps:
1. Pull data from Mongo
1. Vectorize text
1. Compare cosine similarities

To carry out the steps above, I wrote two functions that essentially take care of steps `1` and `3`. Step number `2` simply involved fitting a Pipeline on the original text which vectorized the text using `TfidfVectorizer` and then reduced dimensions using `TruncatedSVD`.

## Built With

- MongoDB
    - pymongo
- AWS t2.micro instance
- Jupyter notebook
- ScikitLearn
- Pandas

## Acknowledgments
- Gus Ostow
- Kevin Cho
