In machine learning,

**over-stemming** and **under-stemming** are two types of errors that occur during the stemming process in Natural Language Processing (NLP), a text preprocessing step. Stemming aims to reduce different forms of a word to a common base form or "stem," which may not be a valid dictionary word. 

Over-Stemming

Over-stemming (or false positive) happens when a stemming algorithm is too aggressive and cuts off too much of a word, reducing two or more semantically different words to the same stem. This can lead to a loss of meaning and conflate unrelated concepts. 

- **Example**: A stemmer might incorrectly reduce both "universal" and "university" to the stem `univers`. These words have distinct meanings and should not be treated as synonyms in a machine learning model, as this could negatively impact tasks like information retrieval or sentiment analysis. 

Under-Stemming

Under-stemming (or false negative) is the opposite problem, occurring when a stemming algorithm is not aggressive enough and fails to reduce related words to the same root form. This results in the model treating words that should be synonyms as different tokens, leading to inconsistencies. 

- **Example**: An algorithm might not stem "alumnus" and "alumni" to the same base form, even though they are inflected forms of the same word (former student). This prevents the model from grouping these related terms, which would be beneficial for tasks like text classification. 

Impact on Machine Learning

The choice of stemming algorithm involves a trade-off between these two errors.