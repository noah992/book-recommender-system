# Book recommendation system
---

[Code](https://github.com/noah992/book-recommender-system/blob/main/code/import.ipynb)
[Dataset](https://github.com/noah992/book-recommender-system/tree/main/data)


## Outline
1. [What is this project?](#what-is-this-project?)
2. [Dataset](#dataset)
3. [How this works](#how-this-works)
5. [Demonstration](#demonstration)
6. [Disclaimer](#disclaimer)
---

## <a name="what-is-this-project?">What is this project?</a>

Tell me your favorite book. I will list some books that you would like.

I assembled book recommendation system.
This system calculates similarity of books based on the reviews and the reviewers and then give you books that has a good similarity score.

---
## <a name="dataset">Dataset</a>
I gained dataset from [Kaggle](https://www.kaggle.com/ruchi798/bookcrossing-dataset) 

Data dictionary
|Column|Type|Description|
|-|-|-|
|ISBN|int|ID for a book|
|User-ID|int|ID of a reviewer|
|Book-Title|string|Book title|
|Book-Rating|int|Rate of the book|

---
## <a name="how-this-works">Eda</a>

I made DataFrame that contains similarily of books to one another using `pair_distances` module and calculated cosine distances based on the book rating.
I used only infuential data, which means that that books have

* No missing values
* More than 50 reviews

This system refers reviews which are given by users, and then calculates relation between books so more reviewers left rating on a book, more useful the book is.
It is better to use books which have many reviews

---
## <a name="demonstration">Demonstration</a>

When I feed a book, `16 Lighthouse Road`, to the system, it returns books which has a similarity score closer to 0.
Closer to 0 the similarity score is, more similar to `16 Lighthouse Road` the book is.

So here is 9 books which are similar to `16 Lighthouse Road` based on reviewers and thier rating.

|Book title|Similarity|
|-|-|
|204 Rosewood Lane|0.719717|
|Macgregor Brides (Macgregors)|0.778454|
|Purity in Death|0.784723|
|Rising Tides|0.796446|
|The Morning After|0.809761|
|Seduction in Death|0.814512|
|Dangerous|0.820282|
|Imitation in Death (Eve Dallas Mysteries (Paperback))|0.822327|
|Girls Night|0.826423|

---
## <a name="disclaimer">Disclaimer</a>

This system constrains books number.
This works certain 1000 books that I used to made this system.

---

#### Credit
Kaggle: https://www.kaggle.com/ruchi798/bookcrossing-dataset
