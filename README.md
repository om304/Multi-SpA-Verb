# Multi-SpA-Verb
Multilingual semantic similarity evaluation resource for verbs in English, Finnish, Italian, Japanese, Polish, and Mandarin Chinese

This repository unifies the datasets introduced in the following papers: 

Olga Majewska, Diana McCarthy, Ivan Vulić, and Anna Korhonen. 2020. “Manual Clustering and Spatial Arrangement of Verbs for Multilingual Evaluation and Typology Analysis”. In Proceedings of COLING 2020 [to appear].

Olga Majewska, Diana McCarthy, Jasper van den Bosch, Nikolaus Kriegeskorte, Ivan Vulić, and Anna Korhonen. 2020.  [__Spatial Multi-Arrangement for Clustering and Multi-way Similarity Dataset Construction__](http://www.lrec-conf.org/proceedings/lrec2020/pdf/2020.lrec-1.705.pdf). In Proceedings of LREC 2020.


## Dataset structure

The dataset includes the following languages: English (en), Finnish (fi), Italian (it), Japanese (ja), Polish (pl), and Mandarin Chinese (zh). In each language-specific folder, included are the following files (each file name starts with a corresponding language ID prefix: en-, fi-, it-, ja-, pl-, zh-):

- verb-classes.txt : the semantic verb classes (Phase 1)

- dataset.txt : the complete pairwise similarity dataset (Phase 2)

- dataset-thr.txt : the thresholded pairwise similarity dataset (Phase 2)


And for each Phase 1 class:

- class#.txt : pairwise similarity scores collected in Phase 2 for verbs in a given class (# - class ID)

Note that the number of classes, as well as their size and underlying semantics, differ across languages (see Tables 1 and 3 in the manuscript), therefore class IDs are language-specific. To facilitate cross-lingual comparisons on similar semantic domains (e.g., verbs of emotion), we provide the following auxiliary files:

- classid-map.txt : mappings of language-specific class IDs (langID) to the cross-lingually aligned class IDs (xlingID) in Table 3 in the paper (note that the cross-lingual alignment is based on overlap in class members, rather than perfect one-to-one mapping between class members in different languages, and English labels used in Table 3 are purely descriptive)

- en-map.txt : word-level mappings (manual translations) between the source language (English) and the target language. Note that the mapping is not perfectly one-to-one: in order to account for the different verb inventories and patterns of ambiguity in the source and target language, a single source word could be translated to multiple target words, and vice versa, multiple source words could be translated to a single target word. For each English word recognised as polysemous, the individual senses identified are numbered (e.g., 1,2...) and mapped to their target language translation.

- en/en-verb-sample.txt : the starting sample of 825 English verbs, translated into each of the languages


## Data format

- verb-classes.txt - one class per line, tab-separated, starting with the class ID 

All pairwise similarity data files start with a header line (“Word1\tWord2\tScore”) and include on each line, tab-separated:

word1 : the first verb of the pair

word2 : the second verb of the pair

score : the similarity score for the pair; note that scores are scaled Euclidean distances, therefore smaller scores signify greater similarity, and larger scores - greater dissimilarity
