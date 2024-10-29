<H3>SAM ISRAEL D</H3>
<H3>212222230128</H3>
<H3>EX. NO.6</H3>
<H3>DATE: 29/10/2024</H3>
<H1 ALIGN =CENTER>Implementation of Semantic ANalysis</H1>
<H3>Aim: to perform Parts of speech identification and Synonym using Natural Language Processing (NLP) techniques. </H3> 
 <BR>
<h3>Algorithm:</h3>
Step 1: Import the nltk library.<br>
Step 2: Download the 'punkt', 'wordnet', and 'averaged_perceptron_tagger' resources.<br>
Step 3:Accept user input for the text.<br>
Step 4:Tokenize the input text into words using the word_tokenize function.<br>
Step 5:Iterate through each word in the tokenized text.<br>
•	Perform part-of-speech tagging on the tokenized words using nltk.pos_tag.<br>
•	Print each word along with its corresponding part-of-speech tag.<br>
•	For each verb , iterate through its synsets (sets of synonyms) using wordnet.synsets(word).<br>
•	Extract synonyms and antonyms using lemma.name() and lemma.antonyms()[0].name() respectively.<br>
•	Print the unique sets of synonyms and antonyms.
<H3>Program:</H3>

##### Importing Necessary Packages

```PYTHON
!pip install nltk
import nltk
from nltk.tokenize import word_tokenize
from nltk.corpus import wordnet
```
##### Downloading NLTK Resources
```python
nltk.download('punkt')
nltk.download('wordnet')
nltk.download('averaged_perceptron_tagger')
```
#### Taking User Input
```python
sentence = input("Enter a sentence: ")
```
#### Tokenizing the Sentence
```python
# Tokenize the sentence into words
words = word_tokenize(sentence)
```
#### Identifying Parts of Speech
```python
# Identify the parts of speech for each word
pos_tags = nltk.pos_tag(words)

# Print the parts of speech
for word, tag in pos_tags:
    print(word, tag)
```
#### Finding Synonyms and Antonyms
```python
# Initialize lists for synonyms and antonyms
synonyms = []
antonyms = []

# Identify synonyms and antonyms for each word
for word in words:
    for syn in wordnet.synsets(word):
        for lemma in syn.lemmas():
            synonyms.append(lemma.name())
            if lemma.antonyms():
                antonyms.append(lemma.antonyms()[0].name())
```
#### Printing Results
```python
# Print the synonyms and antonyms
print("Synonyms:", set(synonyms))
print("Antonyms:", set(antonyms))
```
<H3>Output</H3>

![image](./images/p1.png) 

![image](./images/p2.png)

![image](./images/p3.png)

<H3>Result:</H3>
Thus ,the program to perform the Parts of Speech identification and Synonymis executed sucessfully.
