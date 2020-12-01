# Multi-SpA-Verb
Multilingual semantic similarity evaluation resource for verbs in English, Finnish, Italian, Japanese, Polish, and Mandarin Chinese

This repository unifies the datasets introduced in the following papers: 

Olga Majewska, Diana McCarthy, Ivan Vulić, and Anna Korhonen. 2020. [__Manual Clustering and Spatial Arrangement of Verbs for Multilingual Evaluation and Typology Analysis__](https://www.aclweb.org/anthology/2020.coling-main.423.pdf). In Proceedings of COLING 2020. [CITE](#Cite)

Olga Majewska, Diana McCarthy, Jasper van den Bosch, Nikolaus Kriegeskorte, Ivan Vulić, and Anna Korhonen. 2020.  [__Spatial Multi-Arrangement for Clustering and Multi-way Similarity Dataset Construction__](http://www.lrec-conf.org/proceedings/lrec2020/pdf/2020.lrec-1.705.pdf). In Proceedings of LREC 2020. [CITE](#Cite)


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

## Cite
 
 If you use the data from this repository, please cite:

```
@inproceedings{majewska-etal-2020-manual,
    title = "Manual Clustering and Spatial Arrangement of Verbs for Multilingual Evaluation and Typology Analysis",
    author = "Majewska, Olga  and
      Vuli{\'c}, Ivan  and
      McCarthy, Diana  and
      Korhonen, Anna",
    booktitle = "Proceedings of the 28th International Conference on Computational Linguistics",
    month = dec,
    year = "2020",
    address = "Barcelona, Spain (Online)",
    publisher = "International Committee on Computational Linguistics",
    url = "https://www.aclweb.org/anthology/2020.coling-main.423",
    pages = "4810--4824",
    abstract = "We present the first evaluation of the applicability of a spatial arrangement method (SpAM) to a typologically diverse language sample, and its potential to produce semantic evaluation resources to support multilingual NLP, with a focus on verb semantics. We demonstrate SpAM{'}s utility in allowing for quick bottom-up creation of large-scale evaluation datasets that balance cross-lingual alignment with language specificity. Starting from a shared sample of 825 English verbs, translated into Chinese, Japanese, Finnish, Polish, and Italian, we apply a two-phase annotation process which produces (i) semantic verb classes and (ii) fine-grained similarity scores for nearly 130 thousand verb pairs. We use the two types of verb data to (a) examine cross-lingual similarities and variation, and (b) evaluate the capacity of static and contextualised representation models to accurately reflect verb semantics, contrasting the performance of large language specific pretraining models with their multilingual equivalent on semantic clustering and lexical similarity, across different domains of verb meaning. We release the data from both phases as a large-scale multilingual resource, comprising 85 verb classes and nearly 130k pairwise similarity scores, offering a wealth of possibilities for further evaluation and research on multilingual verb semantics.",
}
```
 
```
 @InProceedings{majewska-EtAl:2020:LREC,
  author    = {Majewska, Olga  and  McCarthy, Diana  and  van den Bosch, Jasper  and  Kriegeskorte, Nikolaus  and  VuliÄ‡, Ivan  and  Korhonen, Anna},
  title     = {Spatial Multi-Arrangement for Clustering and Multi-way Similarity Dataset Construction},
  booktitle      = {Proceedings of The 12th Language Resources and Evaluation Conference},
  month          = {May},
  year           = {2020},
  address        = {Marseille, France},
  publisher      = {European Language Resources Association},
  pages     = {5751--5760},
  abstract  = {We present a novel methodology for fast bottom-up creation of large-scale semantic similarity resources to support development and evaluation of NLP systems. Our work targets verb similarity, but the methodology is equally applicable to other parts of speech. Our approach circumvents the bottleneck of slow and expensive manual development of lexical resources by leveraging semantic intuitions of native speakers and adapting a spatial multi-arrangement approach from cognitive neuroscience, used before only with visual stimuli, to lexical stimuli. Our approach critically obtains judgments of word similarity in the context of a set of related words, rather than of word pairs in isolation. We also handle lexical ambiguity as a natural consequence of a two-phase process where verbs are placed in broad semantic classes prior to the fine-grained spatial similarity judgments. Our proposed design produces a large-scale verb resource comprising 17 relatedness-based classes and a verb similarity dataset containing similarity scores for 29,721 unique verb pairs and 825 target verbs, which we release with this paper.},
  url       = {https://www.aclweb.org/anthology/2020.lrec-1.705}
}
```
