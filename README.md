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
* The vector space model is a V-dimensional space, where V is the vocabulary (set of all words used in documents). Each term in the vocabulary is an axis of the space. 
* Each document, *d* has a position in the vector space that is determined by the words and their frequencies found in *d*. Again, how we choose to compute documents' positions in the vector space is a key design decision. For this lesson, we will implement tf-idf, but I encourage you to explore other vectorization options, such as [doc2vec](https://cs.stanford.edu/~quocle/paragraph_vector.pdf), and decide which works best for your data domain. 

<div style="position:relative;height:600px;width:600px">
<img style="position:absolute; bottom:0; left:0"src="https://github.com/rachelbari/CAPEC-Information-Retrieval/blob/master/static/tfidf-diagram.png" width="350" height="350"> <img style="position:absolute; bottom:0; left:0" src="https://github.com/rachelbari/CAPEC-Information-Retrieval/blob/master/static/vsm-diagram.png" width="425" height="375"> 
</div>

**Document Similarity**
* Once we project our documents into the vector space model, we can compute. 


