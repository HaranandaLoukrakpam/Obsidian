# Natural Language Processing (NLP)

## Definition

**Natural Language Processing (NLP)** is a branch of [[Artificial Intelligence]] that enables computers to understand, interpret, generate, and interact with **human language** in both text and speech. NLP combines concepts from [[Machine Learning]], [[Deep Learning]], [[Computational Linguistics]], and [[Computer Science]] to allow machines to process natural language.

---

## Key Idea

Natural language is the language humans use in everyday communication, such as English, Hindi, or Manipuri.

NLP enables computers to:

- Understand human language.
- Extract useful information.
- Generate meaningful responses.
- Translate between languages.
- Analyze sentiment and emotions.

---

## Goals of NLP

The primary goals of NLP are to:

- Enable human-computer communication.
- Understand the meaning of text and speech.
- Process unstructured language data.
- Generate natural-sounding language.
- Automate language-related tasks.

---

## Components of NLP

NLP is generally divided into two major components:

### [[Natural Language Understanding (NLU)]]

Focuses on understanding the meaning and context of language.

Tasks include:

- Intent recognition
- Named entity recognition
- Sentiment analysis
- Information extraction
- Question answering

---

### [[Natural Language Generation (NLG)]]

Focuses on generating human-like language.

Tasks include:

- Text generation
- Chatbot responses
- Report generation
- Language translation
- Text summarization

---

## NLP Processing Pipeline

1. Collect text or speech data.
2. Preprocess the data.
3. Convert text into numerical representations.
4. Train an NLP model.
5. Evaluate the model.
6. Deploy the model for real-world use.

---

## Common NLP Preprocessing Techniques

### [[Tokenization]]

Splitting text into smaller units called **tokens** (words, sentences, or subwords).

Example:

```
"I love AI."

↓

["I", "love", "AI"]
```

---

### [[Stop Word Removal]]

Removes common words that contribute little meaning.

Examples:

- the
- is
- and
- of
- in

---

### [[Stemming]]

Reduces words to their root form by removing suffixes.

Examples:

- playing → play
- running → run
- connected → connect

---

### [[Lemmatization]]

Converts words to their base (dictionary) form while preserving meaning.

Examples:

- better → good
- running → run
- studies → study

---

### [[Part-of-Speech (POS) Tagging]]

Assigns grammatical categories to words.

Example:

```
The cat runs.

The → Determiner
cat → Noun
runs → Verb
```

---

### [[Named Entity Recognition (NER)]]

Identifies important entities in text.

Examples:

- Person
- Organization
- Location
- Date
- Currency

Example:

```
"Steve Jobs founded Apple."

Steve Jobs → Person
Apple → Organization
```

---

## Text Representation Techniques

### [[Bag of Words (BoW)]]

Represents text based on word frequency.

---

### [[TF-IDF]]

Measures the importance of words within a document relative to a collection of documents.

---

### [[Word Embedding]]

Represents words as dense numerical vectors that capture semantic meaning.

Examples:

- Word2Vec
- GloVe
- FastText

---

### [[Transformer]]

A deep learning architecture that uses attention mechanisms to understand language context.

Examples:

- BERT
- GPT
- T5

---

## Machine Learning in NLP

Traditional NLP uses algorithms such as:

- [[Naive Bayes]]
- [[Support Vector Machine (SVM)]]
- [[Decision Tree]]

Modern NLP uses:

- [[Artificial Neural Network (ANN)]]
- [[Recurrent Neural Network (RNN)]]
- [[Long Short-Term Memory (LSTM)]]
- [[Transformer]]

---

## Common NLP Tasks

### [[Text Classification]]

Assigning predefined categories to text.

Examples:

- Spam detection
- Topic classification

---

### [[Sentiment Analysis]]

Determining whether text expresses positive, negative, or neutral sentiment.

Applications:

- Product reviews
- Social media analysis

---

### [[Machine Translation]]

Automatically translating text between languages.

Example:

```
English → French
English → Hindi
```

---

### [[Question Answering]]

Answering user questions using information from text or knowledge bases.

---

### [[Text Summarization]]

Generating a shorter version of a document while preserving key information.

---

### [[Speech Recognition]]

Converting spoken language into text.

---

### [[Text Generation]]

Automatically generating human-like text.

Examples:

- Chatbots
- Story writing
- Email drafting

---

### [[Information Extraction]]

Extracting useful facts and relationships from text.

---

## Applications of NLP

### Healthcare

- Medical report analysis
- Clinical documentation
- Disease information retrieval

### Finance

- Fraud detection
- News analysis
- Financial document processing

### Education

- Automated grading
- Language learning assistants
- Intelligent tutoring systems

### Customer Service

- Chatbots
- Virtual assistants
- FAQ systems

### Business

- Email classification
- Customer feedback analysis
- Document management

### Social Media

- Sentiment analysis
- Content moderation
- Trend detection

---

## Advantages

- Automates language processing tasks.
- Handles large volumes of text efficiently.
- Improves human-computer interaction.
- Supports multilingual communication.
- Enhances customer experience.
- Enables intelligent search and recommendations.

---

## Limitations

- Ambiguity in human language.
- Difficulty understanding sarcasm and humor.
- Requires large datasets for advanced models.
- Performance depends on language quality and context.
- Computationally intensive for large language models.

---

## NLP vs Human Language Understanding

| NLP | Human Understanding |
|-----|----------------------|
| Learns from data and algorithms | Learns from experience and context |
| Processes text quickly | Better at understanding nuance |
| Can analyze massive datasets | Limited by memory and time |
| May struggle with ambiguity | Naturally understands context and emotion |

---

## Popular NLP Libraries and Frameworks

- [[NLTK]]
- [[spaCy]]
- [[Hugging Face Transformers]]
- [[TensorFlow]]
- [[PyTorch]]
- [[Gensim]]
- [[Stanford CoreNLP]]

---

## Real-World Examples

- ChatGPT
- Google Translate
- Siri
- Alexa
- Google Assistant
- Gmail Smart Compose
- Email spam filtering
- Search engines
- Voice assistants
- Customer support chatbots

---

## Related Notes

- [[Artificial Intelligence]]
- [[Machine Learning]]
- [[Deep Learning]]
- [[Computational Linguistics]]
- [[Natural Language Understanding (NLU)]]
- [[Natural Language Generation (NLG)]]
- [[Tokenization]]
- [[Stop Word Removal]]
- [[Stemming]]
- [[Lemmatization]]
- [[Part-of-Speech (POS) Tagging]]
- [[Named Entity Recognition (NER)]]
- [[Bag of Words (BoW)]]
- [[TF-IDF]]
- [[Word Embedding]]
- [[Transformer]]
- [[Artificial Neural Network (ANN)]]
- [[Recurrent Neural Network (RNN)]]
- [[Long Short-Term Memory (LSTM)]]
- [[Text Classification]]
- [[Sentiment Analysis]]
- [[Machine Translation]]
- [[Speech Recognition]]
- [[Text Summarization]]
- [[Question Answering]]
- [[NLTK]]
- [[spaCy]]
- [[Hugging Face Transformers]]