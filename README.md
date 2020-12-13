# Hackoff 3.0 Siemens Healthineers Challenge 1: KeyBRake - Review Tag Combiner

## Problem Description
Customers write product reviews on ecommerce websites like Amazon. Amazon processes the reviews to generate commonly occurring tags. But, there exist multiple tags referring to the same thing. Create algorithm to combine review tags based on meaning.

## Collaborators
* Stanley Armstrong
* Samuel Frazee
* Kevin Moreland
* Angello Parrolivelli

## Technologies

### Keyword Extraction

#### RAKE (Rapid Automated Keyword Extraction)

**Summary:** RAKE generates all possible candidate keywords from a text, then prioritizes keywords based on co-occurrences with other keywords. These best keywords are then further reduced using other similarity metrics.

[Research paper](https://www.researchgate.net/publication/227988510_Automatic_Keyword_Extraction_from_Individual_Documents)

[rake-nltk](https://pypi.org/project/rake-nltk/)

#### BERT (Bidirectional Encoder Representations from Transformers)

**Summary:** BERT is a model developed by Google to perform bidirectional transformations on words. In our code, we use BERT to tokenize our reviews and then extract keywords using the token representations.

[Research paper](https://arxiv.org/abs/1810.04805)

[KeyBERT](https://github.com/MaartenGr/KeyBERT)

### Tag Grouping

#### WuPalmer Similarity

**Summary:** The WuPalmer similarity finds the semantic similarity of two strings. The score is derived from the distance of one string to another through WordNet, which organizes topics by similarity into a graph for grouping.

[Research paper](https://arxiv.org/abs/cmp-lg/9406033)

#### Matching Similarity
[Research Paper](http://www.cs.joensuu.fi/pages/rezaei/MatchingSimilarity_SSPR2014.pdf)
