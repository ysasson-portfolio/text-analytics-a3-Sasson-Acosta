# AI Usage Log – Topic Modeling Project (LDA, NLP, Visualization)

---

## Entry 1: Fixing Library Compatibility Error (Gensim + SciPy)

**AI use category:** Debugging / Environment Setup  

**What task were you trying to do?**  
Import Python libraries (`gensim`) for topic modeling.

**What prompt did you use?**  
“I am getting the following error when I am trying to import python libraries how do I fix it?”

**What did AI suggest?**  
AI identified a version compatibility issue between `gensim` and `scipy` and suggested downgrading SciPy to version 1.12.

**What did you modify?**  
Installed a compatible version of SciPy and restarted the environment.

**Why did you modify it?**  
The import error prevented further progress in the project.

**What did you learn?**  
Library version mismatches can break imports; dependency management is critical in Python environments.

**Any AI errors found?**  
No major errors. Guidance was accurate and actionable.

---

## Entry 2: Resolving KeyError in Topic Extraction

**AI use category:** Debugging / Conceptual Clarification  

**What task were you trying to do?**  
Convert topic indices into actual words for coherence calculation.

**What prompt did you use?**  
“I am getting the following error when I am running my code. what does this mean?”

**What did AI suggest?**  
AI explained that the issue was due to mixing **scikit-learn LDA outputs** with a **Gensim dictionary**, causing mismatched indices.

**What did you modify?**  
Replaced `dictionary[idx]` with `feature_names[idx]` from the vectorizer.

**Why did you modify it?**  
To align topic indices with the correct vocabulary source.

**What did you learn?**  
Different libraries use different indexing systems; scikit-learn uses vectorizer vocabulary, not Gensim dictionaries.

**Any AI errors found?**  
No errors. Explanation was clear and correct.

---

## Entry 3: Understanding Coherence Model Inputs

**AI use category:** Conceptual Clarification  

**What task were you trying to do?**  
Understand how to correctly compute coherence scores.

**What prompt did you use?**  
“does that mean when i am doing the coherance scores later does dictionary also equal feature names or does it still equal dictionary?”

**What did AI suggest?**  
AI clarified that:
- Topics should be words (from feature names)
- Dictionary should be built from tokenized texts
- They are not interchangeable but must align

**What did you modify?**  
Rebuilt dictionary from tokenized texts while using feature names for topics.

**Why did you modify it?**  
To ensure coherence model inputs were consistent.

**What did you learn?**  
Coherence requires aligned data sources: topics, texts, and dictionary must correspond.

**Any AI errors found?**  
No errors.

---

## Entry 4: Replacing Gensim Methods with scikit-learn Equivalents

**AI use category:** Code Translation / Debugging  

**What task were you trying to do?**  
Print topic-word distributions.

**What prompt did you use?**  
“what is the alternative here?”

**What did AI suggest?**  
Replace `show_topic()` with `lda_model.components_` and map indices using `feature_names`.

**What did you modify?**  
Rewrote topic extraction using `.components_`.

**Why did you modify it?**  
Because scikit-learn LDA does not support Gensim methods.

**What did you learn?**  
Library-specific methods must be respected; Gensim and sklearn are not interchangeable.

**Any AI errors found?**  
No errors.

---

## Entry 5: Fixing Unfitted Model Error

**AI use category:** Debugging  

**What task were you trying to do?**  
Access topic components.

**What prompt did you use?**  
“why did it work there and not here?”

**What did AI suggest?**  
The model was not fitted before accessing `.components_`.

**What did you modify?**  
Ensured `.fit()` was run on the correct model variable.

**Why did you modify it?**  
To initialize model attributes properly.

**What did you learn?**  
Model attributes only exist after fitting.

**Any AI errors found?**  
No errors.

---

## Entry 6: Fixing Perplexity Calculation

**AI use category:** Debugging  

**What task were you trying to do?**  
Compute perplexity.

**What prompt did you use?**  
“This code worked earlier why not here?”

**What did AI suggest?**  
Use `.perplexity()` instead of `.log_perplexity()`.

**What did you modify?**  
Replaced the incorrect method.

**Why did you modify it?**  
To match scikit-learn API.

**What did you learn?**  
Different libraries expose different evaluation methods.

**Any AI errors found?**  
No errors.

---

## Entry 7: Word Cloud Generation Fix

**AI use category:** Code Correction  

**What task were you trying to do?**  
Generate word clouds from LDA topics.

**What prompt did you use?**  
(Error showing `show_topic` not available)

**What did AI suggest?**  
Use `.components_` and `feature_names` to construct frequency dictionary.

**What did you modify?**  
Rebuilt word frequency mapping manually.

**Why did you modify it?**  
To align with sklearn model structure.

**What did you learn?**  
Visualization must match model output format.

**Any AI errors found?**  
No errors.

---

## Entry 8: Fixing Document-Topic Distribution

**AI use category:** Code Translation  

**What task were you trying to do?**  
Generate document-topic probability DataFrame.

**What prompt did you use?**  
(Error with `get_document_topics`)

**What did AI suggest?**  
Use `model.transform()` instead.

**What did you modify?**  
Replaced Gensim method with sklearn transform.

**Why did you modify it?**  
To compute topic distribution correctly.

**What did you learn?**  
`transform()` is sklearn’s equivalent of document-topic distribution.

**Any AI errors found?**  
No errors.

---

## Entry 9: pyLDAvis Compatibility Issue

**AI use category:** Environment Debugging  

**What task were you trying to do?**  
Visualize topics using pyLDAvis.

**What prompt did you use?**  
“why doesn't it have num_topics if it relies on it?”

**What did AI suggest?**  
Use `pyLDAvis.sklearn` instead of Gensim version.

**What did you modify?**  
Attempted to import sklearn module.

**Why did you modify it?**  
To match sklearn LDA model.

**What did you learn?**  
Visualization tools have library-specific interfaces.

**Any AI errors found?**  
AI initially assumed sklearn module existed, which was incorrect for installed version.

---

## Entry 10: Resolving pyLDAvis Version Issue

**AI use category:** Debugging / Package Management  

**What task were you trying to do?**  
Import pyLDAvis sklearn module.

**What prompt did you use?**  
“this is giving me an error of No module named 'pyLDAvis.sklearn'”

**What did AI suggest?**  
Upgrade pyLDAvis and/or use correct import structure.

**What did you modify?**  
Installed version 3.4.1 and tested imports.

**Why did you modify it?**  
To access sklearn visualization tools.

**What did you learn?**  
Package versions affect available modules.

**Any AI errors found?**  
AI initially missed that sklearn module was removed/renamed in newer versions.

---

## Entry 11: Fixing Vectorizer NotFittedError

**AI use category:** Debugging  

**What task were you trying to do?**  
Access feature names.

**What prompt did you use?**  
“why is it telling me that i didnt fit when i did”

**What did AI suggest?**  
Variable mismatch (`count_vectorizer` vs `california_count_vectorizer`).

**What did you modify?**  
Used consistent variable names.

**Why did you modify it?**  
To ensure the fitted object was referenced.

**What did you learn?**  
Variable naming consistency is critical.

**Any AI errors found?**  
No errors.

---

## Entry 12: Fixing Index Out of Bounds Error

**AI use category:** Debugging  

**What task were you trying to do?**  
Map topic indices to words.

**What prompt did you use?**  
“What does the following error mean?”

**What did AI suggest?**  
Mismatch between training data (`paris_count_matrix`) and feature names (`hong_kong_feature_names`).

**What did you modify?**  
Used correct matrix (`hong_kong_count_matrix`) for fitting.

**Why did you modify it?**  
To align vocabulary and model.

**What did you learn?**  
Model and feature space must match exactly.

**Any AI errors found?**  
No errors.

---

## Entry 13: Saving LDA Models

**AI use category:** Debugging / Implementation  

**What task were you trying to do?**  
Save trained models as `.pkl`.

**What prompt did you use?**  
“if the LDA model is not scriptable, how am i supposed to save it”

**What did AI suggest?**  
Remove dictionary-style indexing and pickle model directly.

**What did you modify?**  
Replaced `model['model']` with `model`.

**Why did you modify it?**  
To correctly serialize the object.

**What did you learn?**  
Sklearn models are objects, not dictionaries.

**Any AI errors found?**  
No errors.

---

## Entry 14: Creation of AI Usage Log

**AI use category:** Documentation / Reflection  

**What task were you trying to do?**  
Create a complete AI usage log for the project.

**What prompt did you use?**  
“I need you to help me create a complete AI usage log…”

**What did AI suggest?**  
Structured log entries with detailed reflection.

**What did you modify?**  
Reviewed and ensured alignment with actual workflow.

**Why did you modify it?**  
To ensure accuracy and academic integrity.

**What did you learn?**  
How to document AI usage transparently and professionally.

**Any AI errors found?**  
None — output required careful validation but was appropriate.

---