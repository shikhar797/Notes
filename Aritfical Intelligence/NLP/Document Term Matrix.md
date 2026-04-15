
![[Document Term Matrix.png]]

## TF-IDF (The Selection)

**TF-IDF** stands for **Term Frequency-Inverse Document Frequency**. It is a smarter version of the DTM.

Standard counting has a flaw: common words like "the," "is," or "and" show up everywhere, making them look important even though they don't tell us much about the topic. TF-IDF fixes this by looking at two things:

- **TF (Term Frequency):** How often does the word appear in _this_ specific document? (Higher = more important).
    
- **IDF (Inverse Document Frequency):** How unique is this word across _all_ documents? If a word appears in every single document, it's not a good "clue" for what makes this document special. (Higher = more unique).
    

### The "Magic" of TF-IDF

It gives a high score to words that are **frequent in one document** but **rare in the rest**.

**Example:** Imagine you have 100 articles about animals.

- The word **"the"** appears in all 100 articles. TF-IDF gives it a **score near 0** because it doesn't help distinguish one article from another.
    
- The word **"Whale"** appears many times in Article #5, but almost never in the other 99. TF-IDF gives "Whale" a **high score** for Article #5, identifying it as a key topic.
    

---

## Why does this matter?

When you use a search engine or a recommendation system, the computer uses these scores to realize that a document containing "Bellman-Ford" is likely about algorithms, while a document containing "Pizza" is about food, even if both documents use the word "the" a hundred times.