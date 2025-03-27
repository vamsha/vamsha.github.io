Some of the feature extraction techniques are described below
  1. Bag Of Words (BOW)
  2. N-grams
  3. Term Frequency (TF) - Inverse Document Frequency (IDF)
  4. Tfidftransformer vs. Tfidfvectorizer


**Bag Of Words (BOW)**

The approach is very simple and flexible, and can be used in many ways for extracting features from documents. it involves two things.
- Building the vocabulary
- Counting the occurrence of each word.

Example:
  Collect data

‘All my cats in a row’,
‘When my cat sits down, she looks like a Furby toy!’,


# Welcome to My Website

This is an example of how you can format content using Markdown on GitHub Pages.

## Formatting Text

- **Bold** text: `**Bold**`
- *Italic* text: `*Italic*`
- ~~Strikethrough~~: `~~Strikethrough~~`
- **Combined**: `**_Bold and Italic_**`

## Lists

### Unordered List:
- Item 1
- Item 2
- Item 3

### Ordered List:
1. First item
2. Second item
3. Third item

## Links and Images

- [GitHub](https://github.com)
- ![Image](https://via.placeholder.com/150)

## Code

Inline code: `console.log('Hello World!')`

Code block:
```javascript
function sayHello() {
  console.log("Hello, world!");
}




- **Bag Of Words (BOW)**

  The approach is very simple and flexible, and can be used in many ways for extracting features from documents. it involves two things.
    a. building the vocabulary
    b. counting the occurrence of each word.

Example:
  Collect data

All my cats in a row’,
‘When my cat sits down, she looks like a Furby toy!’,

    Design Vocabulary

Creating the list of words as part of building the vocabulary.

{‘all’: 0, ‘cat’: 1, ‘cats’: 2, ‘down’: 3, ‘furby’: 4, ‘in’: 5, ‘like’: 6, 
‘looks’: 7, ‘my’: 8, ‘row’: 9, ‘she’: 10, ‘sits’: 11, ‘toy’: 12, ‘when’: 13 }

All the above 14 words (dimension) are now our corpus. That means each sentence/document is represented with a length of 14 elements.

    Create the document vectors

‘All my cats in a row’ = [1 0 1 0 0 1 0 0 1 1 0 0 0 0]
‘When my cat sits down, she looks like a Furby toy!’, = [0 1 0 1 1 0 1 1 1 0 1 1 1 1]

We can see that our text (documents) are converted to vectors.

Managing the vocabulary

We can see that the vocabulary size will keep increasing as number of documents increases. We can manage the vocabulary by doing the following.

    ignoring the case
    removing the punctuation
    removing the stop words ( 'in', 'the', 'a')
    misspelling
    stemming/lemmatizing

Problems:

    we lose word order, hence the name "Bag Of Words"
    Counters are not normalized.

sklearn provide a built-in library for the same.

from sklearn.feature_extraction.text import CountVectorizer


corpus = [
'All my cats in a row',
'When my cat sits down, she looks like a Furby toy!',
'The cat from outer space',
'Sunshine loves to sit like this for some reason.'
]


vectorizer = CountVectorizer()
print( vectorizer.fit_transform(corpus).todense() )
print("*****************************************************")
print( vectorizer.vocabulary_ ) 

output:

[[1 0 1 0 0 0 0 1 0 0 0 1 0 0 1 0 0 0 0 0 0 0 0 0 0 0]
 [0 1 0 1 0 0 1 0 1 1 0 1 0 0 0 1 0 1 0 0 0 0 0 0 1 1]
 [0 1 0 0 0 1 0 0 0 0 0 0 1 0 0 0 0 0 0 1 0 1 0 0 0 0]
 [0 0 0 0 1 0 0 0 1 0 1 0 0 1 0 0 1 0 1 0 1 0 1 1 0 0]]
*****************************************************
{'all': 0, 'my': 11, 'cats': 2, 'in': 7, 'row': 14, 'when': 25, 'cat': 1, 
'sits': 17, 'down': 3, 'she': 15, 'looks': 9, 'like': 8, 'furby': 6, 
'toy': 24,'the': 21, 'from': 5, 'outer': 12, 'space': 19, 'sunshine': 20,
'loves': 10,'to': 23, 'sit': 16, 'this': 22, 'for': 4, 'some': 18, 'reason': 13}



N-grams
Term Frequency (TF) - Inverse Document Frequency (IDF)
Tfidftransformer vs. Tfidfvectorizer
