# Information Retrieval for Common Attack Pattern Enumeration and Classification
In this lesson, you will learn learn how to build a basic information retrieval app to search for common attack patterns found on the MITRE CAPEC database. Through this lesson, you will learn about attack patterns employed by adversaries, and natural language processing fundamentals.

# Lesson Skills
* Commmon Attack Patterns
* Natural Language Processing (NLP) and Information Retrieval (IR)
* Web Development with Python

# Background
**CAPEC:**
* Understanding how the adversary operates is essential to effective cyber security. CAPEC™ provides a publicly available catalog of common attack patterns that helps users understand how adversaries exploit weaknesses in applications and other cyber-enabled capabilities. It can be used by analysts, developers, testers, and educators to advance community understanding and enhance defenses. 
* "Attack Patterns" are descriptions of the common attributes and approaches employed by adversaries to exploit known weaknesses in cyber-enabled capabilities. Attack patterns define the challenges that an adversary may face and how they go about solving it. They derive from the concept of design patterns applied in a destructive rather than constructive context and are generated from in-depth analysis of specific real-world exploit examples. Attack patterns help those developing applications, or administrating cyber-enabled capabilities to better understand the specific elements of an attack and how to stop them from succeeding.

**Information Retrieval:**
* Information Retrieval is the task of gathering resources that are revelant to a user's information needs. We use NLP to process documents and extract information. In this lesson, we will be building a document retrieval system that matches user queries with documents in the CAPEC database. 
* There are many different design decisions that comprise an information retrieval system. Two key factors are *document representation* and *document similarity*. 

**Document Representation**
* How the heck do we teach computers to understand human language in documents?! There are many methods that draw from the *vector space model*, which represents queries and documents as vectors in a common vector space.
* The vector space model is a V-dimensional space, where V is the vocabulary (set of all words used in documents). Each term in the vocabulary is an axis of the space. In order to compute document similarity, we will project our documents and the user query in the vector space, then calculate which documents are closest to the query. See *Diagram 1*.
  - [More Notes on Vector Space Model] (https://ils.unc.edu/courses/2013_spring/inls509_001/lectures/06-VectorSpaceModel.pdf)
* Each document, *d* has a position in the vector space that is determined by the words and their frequencies found in *d*. Again, how we choose to compute documents' positions in the vector space is a key design decision. For this lesson, we will implement tf-idf, but I encourage you to explore other vectorization options, such as [doc2vec](https://cs.stanford.edu/~quocle/paragraph_vector.pdf), and decide which works best for your data domain. 
* To start, we will use a *bag of words (BoW) model*, a vector representation that ignores word ordering in a document. 
  - [More Notes on Bag of Words] (https://medium.com/greyatom/an-introduction-to-bag-of-words-in-nlp-ac967d43b428)
* In order to transform our documents into the vector space, we can convert a collection of text documents to a matrix of token counts, with dimensions *V x D*, where V is the number of words in the vocabulary and D is the number of documents. Each document, *d* is represented as a count vector, meaning it contains the number of times each word in V appears in *d*. 
* TF-IDF is a weighting scheme that we apply to the term-document count matrix to reflect "how important" a word is to a document in a collection. Term frequency (tf) is the number of times a term, *t* appears in document *d*, and inverse document frequency (idf) is the inverse of the number of documents that contain *t*. 
  - [More Notes on TF-IDF](https://web.stanford.edu/class/cs276/handouts/lecture6-tfidf-handout-1-per.pdf)

<div>
<img src="https://github.com/rachelbari/CAPEC-Information-Retrieval/blob/master/static/vsm-diagram.png" width="375" height="375"> <img src="https://github.com/rachelbari/CAPEC-Information-Retrieval/blob/master/static/count-matrix-diagram.png" width="425" height="375">
</div>
<br>
<br>

**Document Similarity**
* Once we project our documents into the vector space model, we can compute. 


