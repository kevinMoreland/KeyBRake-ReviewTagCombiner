# Hackoff 3.0 Siemens Healthineers Challenge 1: KeyBRake - Review Tag Combiner

**The included notebook was developed in Google Colab, and will not work out of the box without modifications and the json file mounted through Google Drive.**

## Problem Description
Customers write product reviews on ecommerce websites like Amazon. Amazon processes the reviews to generate commonly occurring tags. But, there exist multiple tags referring to the same thing. Create algorithm to combine review tags based on meaning.

## Collaborators
* Stanley Armstrong
* Samuel Frazee
* Kevin Moreland
* Angello Parrolivelli

## Data

Data used for this project is Amazon product reviews from the years 2012 - 2014 for various products. This is not a complete dataset of all reviews for these products. The data is in JSON format and can be found as a direct download from [https://bit.ly/SHPL1](here) or you can view the source of this data [http://jmcauley.ucsd.edu/data/amazon/](here) (our data is found under "Small" subsets for experimentation > Cell Phones and Accessories).

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

**Summary:** The WuPalmer similarity finds the similarity of two strings based on the depths of where their synonym sets meet. We use this to find the number of similar words between two keywords/phrases. If they are similar, they are organized into the same tag group.

[Research Paper](http://www.cs.joensuu.fi/pages/rezaei/MatchingSimilarity_SSPR2014.pdf)
