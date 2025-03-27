---
title: NLTK
layout: default
---

NLTK is a leading platform for building Python programs to work with human language data. Natural Language Processing with Python provides a practical introduction to programming for language processing.A lot of text mining or text analysis things NLTK can do, we will introduce them below.

    - Stop words
    - word_tokenize & sent_tokenize
    - Parts_Of_Speech tagging
    - Stemming and Lemmatisation

## Stop words

Definition from [wiki](https://en.wikipedia.org/wiki/Stop_word) : stop words are words which are filtered out before or after processing of natural language data (text).Though "stop words" usually refers to the most common words in a language, there is no single universal list of stop words used by all natural language processing tools, and indeed not all tools even use such a list. Some tools specifically avoid removing these stop words to support phrase search. Any group of words can be chosen as the stop words for a given purpose. For some search engines, these are some of the most common, short function words, such as "the, is, at, which, and on".

Stop words from English corpus of NLTK:
```
{'such', 'same', 'those', 'against', 'be', 'did', 'if', 'just', 'both', 'they', 
'ain', 'mightn', 'because', 'having', "haven't", 'being', 'has', 'ours', 
'herself', "it's", 'very', 'wasn', 'won', 'into', 'd', 'been', 'when', 'them', 
'from', 'over', 'in', 'before', 'these', "you'd", 'hadn', 'above', "hasn't", 
"doesn't", 'too', 'isn', 'now', "shan't", 'yourselves', 'why', 'that', 'own', 
'each', 'don', 'or', "hadn't", 'himself', 'off', 'is', 'shan', 'it', 'theirs', 
'o', 'i', 'more', 'only', 'out', 'again', 'itself', 'to', 'we', 'her', 'as', 
'our', "wasn't", 'had', 'this', 'myself', 'so', "needn't", 'do', 'hasn', 'have',
 'most', "should've", "weren't", 'some', 'how', 'm', 'other', 'with', 'than', 
'who', "you've", 'under', 're', 'ma', 'below', 'after', 's', 'few', 'my', 'not',
'doesn', 'between', 'on', 'mustn', 'doing', "isn't", 'yourself', 'through', 
'wouldn', 'then', 'up', 'can', "shouldn't", 'him', 'and', 'there', 'where', 
'weren', "aren't", 'are', 'am', 'were', 'once', "mightn't", 'ourselves', 'by', 
"couldn't", 'nor', 'their', 'what', 'for', "you're", 'y', 'the', 'until', 
'couldn', 'while', 'here', 'whom', "she's", "won't", 'haven', 'she', 'his', 
'during', 'its', 'which', 'of', 'was', 'didn', 'at', 'a', 'should', 'an', 
"that'll", 'yours', "you'll", 'he', 'down', 'needn', 't', 've', 'but', 'does', 
'any', 'no', 'your', "mustn't", "wouldn't", 'aren', "didn't", 'll', 'themselves',
 'further', 'you', 'me', 'will', 'shouldn', 'about', 'hers', "don't", 'all'}
```

```
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize

text = "i am tring to remove the stop words from atext as part of learning"
words = word_tokenize(text)
print(words)
```

```
['i', 'am', 'tring', 'to', 'remove', 'the', 'stop', 'words', 'from', 'atext', 
'as', 'part', 'of', 'learning']
```

```
stop_words = set(stopwords.words('english'))
sentence_no_stopwords = [w for w in words if not w in stop_words]
print(sentence_no_stopwords)
```

```
['tring', 'remove', 'stop', 'words', 'atext', 'part', 'learning']
```


## word_tokenize & sent_tokenize

There are many nlp tools include the sentence tokenize function, such as OpenNLP，NLTK, TextBlob, MBSP and etc. Here we will discuss about NLTK .

**Tokenizing** : Splitting the sentences into word or sentences.

we do have predefined modules in NLTK to perform the word tokenize and sentence tokenize.
```
from nltk.tokenize import sent_tokenize, word_tokenize

text = """The problem is that things like Mr. Smith would cause you trouble,
and many other things. Splitting by word is also a challenge, especially when
considering things like concatenations like we and are to we're.
NLTK is going to go ahead and just save you a ton of time with this seemingly
simple, yet very complex, operation."""

sentences = sent_tokenize(text)

print("sentences are", sentences)
sentences are :  ['The problem is that things like Mr. Smith would cause you trouble,\nand many other things.', 
"Splitting by word is also a challenge, especially when\nconsidering things like concatenations like we and are to we're.", 
'NLTK is going to go ahead and just save you a ton of time with this seemingly\nsimple, yet very complex, operation.']

print(len(sentences))
3
```
```
words = word_tokenize(text)
print("words are", words)
words are :  ['The', 'problem', 'is', 'that', 'things', 'like', 'Mr.', 'Smith', 'would', 'cause', 'you', 'trouble', ',', 'and', 'many', 'other', 'things', '.', 'Splitting', 'by', 'word', 'is', 'also', 'a', 'challenge', ',', 'especially', 'when', 'considering', 'things', 'like', 'concatenations', 'like', 'we', 'and', 'are', 'to', 'we', "'re", '.', 'NLTK', 'is', 'going', 'to', 'go', 'ahead', 'and', 'just', 'save', 'you', 'a', 'ton', 'of', 'time', 'with', 'this', 'seemingly', 'simple', ',', 'yet', 'very', 'complex', ',', 'operation', '.']
```

There are total 17 european languages ( https://github.com/alyssaq/nltk_data/blob/master/tokenizers/punkt/README ) that NLTK support for sentence tokenize, and you can use them as the following steps:
```
import nltk.data
text = """this’s a sent tokenize test. this is sent two. is this sent three? 
sent 4 is cool! Now it’s your turn."""
tokenizer = nltk.data.load('tokenizers/punkt/english.pickle')
print(tokenizer.tokenize(text))
['this’s a sent tokenize test.', 'this is sent two.', 'is this sent three?', 
'sent 4 is cool!', 'Now it’s your turn.']


spanish_tokenizer = nltk.data.load('tokenizers/punkt/spanish.pickle')
print(spanish_tokenizer.tokenize("Hola amigo. Estoy bien."))
['Hola amigo.', 'Estoy bien.']
```


## Parts_Of_Speech tagging

Definition from [Wikipedia](https://en.wikipedia.org/wiki/Part-of-speech_tagging) : part-of-speech tagging (POS tagging or PoS tagging or POST), also called grammatical tagging or word-category disambiguation, is the process of marking up a word in a text (corpus) as corresponding to a particular part of speech,[1] based on both its definition and its context—i.e., its relationship with adjacent and related words in a phrase, sentence, or paragraph. A simplified form of this is commonly taught to school-age children, in the identification of words as nouns, verbs, adjectives, adverbs, etc.

POS tagging in NLTK:
```
import nltk
text = nltk.word_tokenize("Part-of-speech tagging and POS Tagger")
print(text)
print(nltk.pos_tag(text))

['Part-of-speech', 'tagging', 'and', 'POS', 'Tagger']
[('Part-of-speech', 'JJ'), ('tagging', 'NN'), ('and', 'CC'), ('POS', 'NNP'), ('Tagger', 'NNP')]
```
```
Part-of-Speech Tag set:
    CC coordinating conjunction
    CD cardinal digit
    DT determiner
    EX existential there (like: "there is" ... think of it like "there exists")
    FW foreign word
    IN preposition/subordinating conjunction
    JJ adjective 'big'
    JJR adjective, comparative 'bigger'
    JJS adjective, superlative 'biggest'
    LS list marker 1)
    MD modal could, will
    NN noun, singular 'desk'
    NNS noun plural 'desks'
    NNP proper noun, singular 'Harrison'
    NNPS proper noun, plural 'Americans'
    PDT predeterminer 'all the kids'
    POS possessive ending parent's
    PRP personal pronoun I, he, she
    PRP$ possessive pronoun my, his, hers
    RB adverb very, silently,
    RBR adverb, comparative better
    RBS adverb, superlative best
    RP particle give up
    TO to go 'to' the store.
    UH interjection errrrrrrrm
    VB verb, base form take
    VBD verb, past tense took
    VBG verb, gerund/present participle taking
    VBN verb, past participle taken
    VBP verb, sing. present, non-3d take
    VBZ verb, 3rd person sing. present takes
    WDT wh-determiner which
    WP wh-pronoun who, what
    WP$ possessive wh-pronoun whose
    WRB wh-abverb where, when
```

## Stemming

Stemming and Lemmatization are the basic text processing methods for English text. The goal of both stemming and lemmatization is to reduce inflectional forms and sometimes derivationally related forms of a word to a common base form.

Stemming Definition from [wiki](https://en.wikipedia.org/wiki/Stemming) : stemming is the process of reducing inflected (or sometimes derived) words to their word stem, base or root form—generally a written word form. The stem need not be identical to the morphological root of the word; it is usually sufficient that related words map to the same stem, even if this stem is not in itself a valid root. Many search engines treat words with the same stem as synonyms as a kind of query expansion, a process called conflation.

NLTK provides several famous stemmers interfaces, such as [Porter stemmer](http://textanalysisonline.com/nltk-porter-stemmer), [Lancaster Stemmer](http://textanalysisonline.com/nltk-lancaster-stemmer), [Snowball Stemmer](http://textanalysisonline.com/nltk-snowball-stemmer) and etc.

```
rom nltk.stem import PorterStemmer
from nltk.tokenize import sent_tokenize, word_tokenize

ps = PorterStemmer()

print(ps.stem("analysing"))
print(ps.stem("analyse"))
print(ps.stem("analysed"))
print(ps.stem("String"))
print(ps.stem("driving"))
print(ps.stem("saying"))

output:

analys
analys
analys
string
drive
say
```

## Lemmatisation:

Definition from [wiki](https://en.wikipedia.org/wiki/Lemmatisation) : lemmatisation is the algorithmic process of determining the [lemma](https://en.wikipedia.org/wiki/Lemma_(morphology)) of a word based on its intended meaning. Unlike [stemming](https://en.wikipedia.org/wiki/Stemming), lemmatisation depends on correctly identifying the intended [part of speech](https://en.wikipedia.org/wiki/Part_of_speech) and meaning of a word in a sentence, as well as within the larger context surrounding that sentence, such as neighboring sentences or even an entire document.

The NLTK Lemmatization method is based on WordNet’s built-in morphy function. Here is the introduction from [WordNet](http://wordnet.princeton.edu/) official website:

```
from nltk.stem import WordNetLemmatizer
wl = WordNetLemmatizer()


print(wl.lemmatize('dogs'))
print(wl.lemmatize('churches'))
print(wl.lemmatize('are'))
print(wl.lemmatize('is'))

output:

dog
church
are
is
```

You would note that the "are" and "is” lemmatize results are not "be”, that’s because the lemmatize method default pos argument is "n”:

lemmatize(word, pos='n')

So you need specified the pos for the word like below:
```
print(wl.lemmatize('are', pos = 'v')) # v stands for VERB
print(wl.lemmatize('is', pos = 'v'))

output:
be
be
```

Difference between Stemming and Lemmatisation is
- A stemmer will return the stem of a word, which needn't be identical to the morphological root of the word. It usually sufficient that related words map to the same stem,even if the stem is not in itself a valid root, while in lemmatisation, it will return the dictionary form of a word, which must be a valid word.
- In lemmatisation, the part of speech of a word should be first determined and the normalization rules will be different for different part of speech, while the stemmer operates on a single word without knowledge of the context, and therefore cannot discriminate between words which have different meanings depending on part of speech.


**References:**
- https://pythonprogramming.net/natural-language-toolkit-nltk-part-speech-tagging/
- https://textminingonline.com/
- https://stackoverflow.com/questions/1787110/what-is-the-true-difference-between-lemmatization-vs-stemming




















