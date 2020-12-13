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

Data used for this project is Amazon product reviews from the years 2012 - 2014 for various products. This is not a complete dataset of all reviews for these products. The data is in JSON format and can be found as a direct download from [here](https://bit.ly/SHPL1) or you can view the source of this data [here](http://jmcauley.ucsd.edu/data/amazon/) (our data is found under "Small" subsets for experimentation > Cell Phones and Accessories).

## Technologies

### Keyword Extraction

#### RAKE (Rapid Automated Keyword Extraction)

**Summary:** RAKE generates all possible candidate keywords from a text, then prioritizes keywords based on co-occurrences with other keywords. These best keywords are then further reduced using other similarity metrics. The primary metric of judging keywords is based on the degree of words, frequency of words, or degree to frequency ratio (d(w)/f(w)).

[Research paper](https://www.researchgate.net/publication/227988510_Automatic_Keyword_Extraction_from_Individual_Documents)

[rake-nltk](https://pypi.org/project/rake-nltk/)

#### BERT (Bidirectional Encoder Representations from Transformers)

**Summary:** BERT is a model developed by Google to perform bidirectional transformations on words. In our code, we use BERT to tokenize our reviews and then extract keywords using the token representations. BERT judges keywords based on semantic analysis and is trained on data from Wikipedia.

[Research paper](https://arxiv.org/abs/1810.04805)

[KeyBERT](https://github.com/MaartenGr/KeyBERT)

### Tag Grouping

#### WuPalmer Similarity

**Summary:** The WuPalmer similarity finds the similarity of two words based on the depths of where their synonym sets meet. We use this to compare every word in each key phrase with every word in another, and get a similarity score. Key phrases that are determined to be similar are then organized into the same tag group.

[Research Paper](http://www.cs.joensuu.fi/pages/rezaei/MatchingSimilarity_SSPR2014.pdf)

## Conclusion

We make use of BERT and Rake to get different types of keywords per product based on lots of product reviews. The more reviews, the better these technologies are. We then compile these keywords (which are product tags) and try to group them together by using the WuPalmer similarity and some custom-made tolerances and comparisons. If the probability is high that the product tags are similar in meaning, we put them together in a TagGroup. We end up with a list of TagGroups that show which tags have the same meanings written differently.
