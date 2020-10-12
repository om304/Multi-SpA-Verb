# Multi-SpA-Verb
Multilingual semantic similarity evaluation resource for verbs

This repository contains the Supplementary Material for the COLING 2020 submission: “Manual Clustering and Spatial Arrangement of Verbs for Multilingual Evaluation and Typology Analysis”.


## Files

The complete language-specific data produced in the study and used for model evaluation:
	fi/ (Finnish)
	it/ (Italian)
	ja/ (Japanese)
	pl/ (Polish)
	zh/ (Mandarin Chinese)
	

## Dataset structure

In each language-specific folder, included are the following files (each file name starts with a corresponding language ID prefix: zh-, ja-, fi-, it-, pl-):

- verb-classes.txt : the semantic verb classes (Phase 1)
- dataset.txt : the complete pairwise similarity dataset (Phase 2)
- dataset-thr.txt : the thresholded pairwise similarity dataset (Phase 2)

And for each Phase 1 class:
- class#.txt : pairwise similarity scores collected in Phase 2 for verbs in a given class (# - class ID)

Note that the number of classes, as well as their size and underlying semantics, differ across languages (see Tables 1 and 3 in the manuscript), therefore class IDs are language-specific. To facilitate cross-lingual comparisons on similar semantic domains (e.g., verbs of emotion), we provide the following auxiliary file:

- classid-map.txt : mappings of language-specific class IDs (langID) to the cross-lingually aligned class IDs (xlingID) in Table 3 in the paper (note that the cross-lingual alignment is based on overlap in class members, rather than perfect one-to-one mapping between class members in different languages, and English labels used in Table 3 are purely descriptive)


## Data format

- verb-classes.txt - one class per line, tab-separated, starting with the class ID 

All pairwise similarity data files start with a header line (“Word1\tWord2\tScore”) and include on each line, tab-separated:

# word1 : the first verb of the pair

# word2 : the second verb of the pair

# score : the similarity score for the pair; note that scores are scaled Euclidean distances, therefore smaller scores signify greater similarity, and larger scores - greater dissimilarity
