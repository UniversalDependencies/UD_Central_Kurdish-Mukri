<<<<<<< HEAD
# Central Kurdish Universal Dependencies Treebank

UD Version: 2
Language: Mukri Kurdish
Script: Kurdish-Roman Alphabet
License: CC BY-SA 4.0

---

# Overview

This treebank contains manually annotated data for Mukri Kurdish (Indo-European) belonging to Kurdish language family, following the Universal Dependencies (UD) guidelines. It aims to offer a syntactically and morphologically consistent dataset that helps with Kurdish language processing and cross-linguistic studies. The current release includes texts in Kurdish Roman Alphabet script and provides dependency annotation at the word, phrase, and sentence levels.

---

# Data Format

The data is stored in .conllu format, which is standard in UD. Each sentence is tokenized, lemmatized, POS-tagged, and labeled with syntactic dependencies.

A typical entry looks like this:

1   Lew   l+ew   ADP   _   _   2   case   _   _
2   mal   mal     NOUN  _   Number=Sing|Definite=Def   0   root   _   _

---

## Each token includes:

    ID

    FORM (surface word)

    LEMMA

    UPOS (universal POS)

    XPOS (language-specific POS, unused here)

    FEATS (morphological features)

    HEAD (governor in the tree)

    DEPREL (relation to the HEAD)

    DEPS (enhanced dependencies, not used here)

    MISC (comments)

---

# Tokenization and Word Segmentation

Tokenization follows standard rules using whitespace and punctuation. However, due to the nature of Kurdish, additional processing is required.

---

## How things are handled:

### Multiword Tokens: Some written words contain multiple grammatical units, which are split into smaller parts.

        Example: meseleyēkit → meseleyēk (an issue) + it (your)

        These are represented as single orthographic tokens that expand into multiple syntactic words in the .conllu file.

### Clitics and Enclitics: Kurdish often attaches pronouns, case markers, and particles to other words. These are segmented and labeled properly.

        xoy → xo + y (reflexive + pronoun)

### Contracted Prepositions:

        Lew → L (preposition) + ew (determiner)

### Special Symbols: 
        
        Curly braces {} and hash signs # are used in the raw data for editorial corrections. These are left in the comments or cleaned during preprocessing.

---

# Part-of-Speech Tagging

The POS tags follow the universal POS tagset. All major categories are used. Some details on how tagging decisions are made:

| POS                            | Notes                                                                                                             |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------- |
| **NOUN**                       | Includes common and proper nouns.                                                                                 |
| **VERB**                       | Used for full verbs.                                                                                              |
| **AUX**                        | Covers copulas and auxiliaries like 'e' (is).                                                                     |
| **PART**                       | Used for discourse particles ('yānī'), reflexives ('xo'), modals ('bā'), negation ('ne'), and coordinators ('ū'). |
| **DET** vs **PRON**            | Determiners are words like 'ew' when used with nouns; pronouns are used independently.                            |
| **ADP**                        | Used for prepositions, even if attached to other words.                                                           |
| **ADJ**, **ADV**               | Deverbal forms are tagged based on usage (e.g. if a verb form modifies a noun, it may be tagged as ADJ).          |
| **CCONJ**, **SCONJ**, **INTJ** | Coordinators, subordinators, and interjections are tagged accordingly.                                            |

---

# Morphological Features

Each word may be annotated with features like number, person, gender, definiteness, etc. Below are key features and how they’re used in the dataset:

---

## Nouns

    Number: Singular or Plural

    Definite:

        Def: The (definite)

        Ind: A/an (indefinite)

        Spec: Specific (but not definite)

    Person: Some nouns (especially kinship terms) can take possessive suffixes (e.g. mother-my)

---

## Verbs

    VerbForm: Finite (main verbs) or Infinitive

    Mood: Indicative (normal), Subjunctive, or Imperative

    Tense: Present or Past

    Person/Number: Agreement with subject

    Voice: Active or Passive

    Aspect: Mostly Imp (imperfective) used with certain past forms

---

## Pronouns

    Person: 1st, 2nd, 3rd

    Number: Singular, Plural

    Reflex: Marked when the pronoun refers back to the subject

---

## Others

    ExtPos: Used when a word behaves syntactically like another POS (e.g. a noun behaving like a postposition)

---

# Syntax and Dependency Relations

The treebank uses standard UD dependency labels. Relations follow syntactic rules of Southern Kurdish, which often uses SOV word order and ergative alignment in past tense.
Main Relation Types


| Relation       | Explanation                                             |
| -------------- | ------------------------------------------------------- |
| 'nsubj'        | Marks the subject of the clause                         |
| 'obj'          | Direct object                                           |
| 'iobj'         | Indirect object (usually with benefactive meaning)      |
| 'obl'          | Oblique argument, includes locations, instruments, etc. |
| 'cop'          | Used with the copula verb (e.g., 'e', 'ne')             |
| 'compound:lvc' | Light verb constructions (very common)                  |
| 'nmod:poss'    | Possessive noun modifiers                               |
| 'acl:relcl'    | Relative clauses                                        |

---

## Notes on Syntax

    Copula: The verb e is often used to link subjects and complements. It can be omitted in present tense (zero copula).

    Light Verb Constructions: These are phrases like “decision take” instead of a simple verb like “decide.” They are labeled with compound:lvc.

    Relative Clauses: Annotated with acl:relcl

    Ergativity: In past tense, the subject of a transitive verb may carry oblique marking, and this is reflected in dependency labels.

---

# Treebank Details

Currently, this release includes one annotated treebank:

| Name                      | Code         | Description                                                 |
| ------------------------- | ------------ | ----------------------------------------------------------- |
| Central Kurdish - Mukri   | 'ckb_mukri'  | Sentences in the Sorani variety using Roman-Alphabet script |


All data is manually reviewed. Automated scripts are used for consistency checks.

---

# Tools & Usage

You can load and analyze this dataset using tools like:

    UDPipe

    Stanza

    UD Annotatrix

    Any .conllu viewer/editor

---

# Contact & License

- **Lead Maintainer**: Hiwa Asadpour — overall coordination, main annotation, and releases
- **Contributors**: 
- **Email**: [asadpourhiwa@gmail.com]
- **License**: [CC-BY 4.0]

You are free to share and adapt this work with proper attribution.

---

# Citation

If you use this dataset, please cite the work as:

@misc{centralkurdishud2025,
  title     = {Central Kurdish-Mukri Universal Dependencies Treebank},
  author    = {Asadpour, Hiwa},
  year      = {2025},
  howpublished = {\url{https://universaldependencies.org/treebanks/ckb_mukri/}},
  note      = {Universal Dependencies v2}
}


---

# Notes

This treebank is still evolving. Updates may include more sentences, improved consistency, and refined morphological analysis.

For more detailed explanation of tagging and labeling, refer to the UD Guidelines.


# Reference

* 2022a	Asadpour, Hiwa. Parts of Speech and the placement of Targets in the corpus of languages in northwestern Iran. Corpus Linguistics and Linguistic Theory. De Gruyter Mouton.

* 2022b	Asadpour, Hiwa. Word order in Mukri Kurdish – the case of incorporated Targets. In Hiwa Asadpour and Thomas Jügel (eds.), Word Order Variation: Semitic, Turkic, and Indo-European Languages in contact, Studia Typologica [STTYP] 31. 63-88. Berlin & Boston: De Gruyter Mouton.

* 2022c	Asadpour, Hiwa, Shene Othoman and Manfred Sailer. Non-“wh” relatives in English and Kurdish: Constraints on grammar and use. HPSG 2022 (29th International Conference on Head-Driven Phrase Structure Grammar). Online Event, JP.

* 2021	Asadpour, Hiwa. Cross-Dialect Diversity in Mukri Kurdish I: Phonological and Phonetic variation at Linguistic Geography, Cambridge University Press.


---
=======
# Summary

... 1-2 sentences (see [release checklist](http://universaldependencies.org/contributing/release_checklist.html#the-readme-file) for README guidelines) ...


# Introduction

...


# Acknowledgments

...

## References

* (citation)

>>>>>>> 9e5f537cd4188bb04f0c2947eb040b7750e34be4

# Changelog

* 2025-11-15 v2.17
  * Initial release in Universal Dependencies.


<pre>
=== Machine-readable metadata (DO NOT REMOVE!) ================================
Data available since: UD v2.17
License: CC BY-SA 4.0
Includes text: yes
Genre: grammar-examples
Lemmas: manual native
UPOS: manual native
XPOS: not available
Features: manual native
Relations: manual native
<<<<<<< HEAD
Contributors: Talamo, Luigi; Asadpour, Hiwa; Verkerk, Annemarie; Vaz, Helena
Contributing: here
Contact: luigi.talamo@uni-saarland.de
===============================================================================
</pre>
=======
Contributors: Asadpour, Hiwa
Contributing: here
Contact: asadpourhiwa@gmail.com
===============================================================================
</pre>
>>>>>>> 9e5f537cd4188bb04f0c2947eb040b7750e34be4
