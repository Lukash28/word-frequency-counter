# Word Frequency Counter

A simple Python script that reads a text file, counts how often each word appears,  
and displays the **Top 10 most frequent words**.
This mini project was created as part of learning Python basics — file handling, loops, dictionaries, and string processing.

##  How It Works

1. The program asks you to enter a file name (for example: `text.txt`)
2. It reads the text and removes punctuation
3. Converts all words to lowercase
4. Counts how often each word appears
5. Displays the 10 most frequent words

##  Example

**Input file (`text.txt`):**

Artificial intelligence is changing the world.
AI is used in phones, cars, healthcare, and many other industries.
Python is one of the most popular programming languages for AI.
Machine learning allows computers to learn from data.

**Program output:**

Top 10 words
is 5
the 3
ai 3
artificial 2
intelligence 2
world 2
and 2
of 2
learning 2
changing 1


---

## 🛠️ Code

```python
import string

filename = input('Enter file name: ').strip()

try:
    fh = open(filename, 'r')
except:
    print("File cannot be opened:", filename)
    quit()

word_counts = {}

for line in fh:
    line = line.strip()
    words = line.split()
    for word in words:
        word = word.lower().strip(string.punctuation)
        if word:
            word_counts[word] = word_counts.get(word, 0) + 1

fh.close() 	

sorted_words = sorted(word_counts.items(), key=lambda x: x[1], reverse=True)

print('\nTop 10 words:')
for word, count in sorted_words[:10]:
    print(word, count)
```
  Skills Practiced
1)File handling (open, read, strip)
2)Dictionaries and word frequency counting
3)String manipulation (lower(), strip(), split())
4)Sorting with lambda functions
5)Basic text processing and cleanup


Created by Lukash Leshchuk
Python learning project – 2025


