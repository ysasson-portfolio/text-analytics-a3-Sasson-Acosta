# AI Usage Log

This log documents approved AI use during Assignment 3 for Text Mining and Social Media Analytics. The entries below focus on the areas where AI was actually used in a meaningful way: debugging notebook issues, clarifying Jupyter/GitHub workflow concepts, explaining model-evaluation concepts, and troubleshooting environment or file-management problems.

The final NMF implementation itself was primarily built by following the professor’s example notebook and adapting it to the project structure. AI support was mainly used to diagnose errors, clarify workflow decisions, and explain technical concepts.

---

## Log Entry 1

**1. AI use category**  
Concept explanations, syntax / API questions

**2. What task were you trying to do?**  
I was trying to understand how data was being passed between notebooks and whether `%store` was something shared through GitHub.

**3. What prompt did you use?**  
I asked whether the stored dataframe was part of GitHub as a whole and whether I needed to run the preprocessing notebook with my own path.

**4. What did AI suggest?**  
AI explained that:
- `%store` is local to the Jupyter/IPython environment
- it is not shared through GitHub
- a processed CSV is a better collaborative handoff between notebooks
- relative file paths are better than machine-specific paths for a shared repository

**5. What did you modify?**  
I changed how I understood the workflow and moved toward using a processed CSV export rather than depending only on `%store`.

**6. Why did you modify it?**  
I needed a setup that would work across both my machine and my groupmate’s machine.

**7. What did you learn?**  
I learned the difference between local notebook memory/state and shareable repo-based files, and why `%store` is not a collaborative solution.

**8. Any AI errors found?**  
No major errors. This was a conceptual clarification that helped me understand the notebook workflow.

---

## Log Entry 2

**1. AI use category**  
Debugging errors, syntax / API questions

**2. What task were you trying to do?**  
I was trying to run `01_eda.ipynb` on my Mac, but the notebook had a Windows file path and I needed to make it work with the local GitHub repo structure.

**3. What prompt did you use?**  
I asked how to make sure the notebook was loading from the GitHub repository folders rather than a personal file path, and whether Jupyter “pulls from GitHub directly.”

**4. What did AI suggest?**  
AI explained that:
- Jupyter runs from the local copy of the repo, not GitHub directly
- I should use relative paths instead of personal absolute paths
- I should test the working directory with `os.getcwd()`
- the correct path likely depended on whether the notebook was running from the repo root or the `notebooks` folder

**5. What did you modify?**  
I changed the raw CSV path in `01_eda.ipynb` to a relative repo path that worked on my machine.

**6. Why did you modify it?**  
The original hardcoded Windows path could not work on my Mac, and I needed the notebook to run from the shared repo structure.

**7. What did you learn?**  
I learned how Jupyter resolves file paths relative to the notebook’s working directory and why shared notebooks should use relative paths.

**8. Any AI errors found?**  
No major errors. I still verified the exact correct path myself in Jupyter.

---

## Log Entry 3

**1. AI use category**  
Debugging errors

**2. What task were you trying to do?**  
I was trying to run `02_preprocessing.ipynb`, but I got an import error related to package compatibility.

**3. What prompt did you use?**  
I showed the import block and the traceback and asked how to correct the error with minimal changes to my groupmate’s code.

**4. What did AI suggest?**  
AI suggested that the problem was likely caused by a package compatibility issue rather than the notebook logic itself. It recommended:
- commenting out non-essential imports that were not needed for preprocessing
- keeping the core preprocessing imports
- isolating whether the issue came specifically from `spacy`

**5. What did you modify?**  
I simplified the import block by commenting out extra topic-modeling and visualization imports that were not needed for preprocessing.

**6. Why did you modify it?**  
I wanted to preserve the real preprocessing logic while removing unnecessary sources of import errors.

**7. What did you learn?**  
I learned that notebooks sometimes include extra imports that are not essential to the task at hand, and those imports can create environment-specific issues.

**8. Any AI errors found?**  
The first round of troubleshooting did not fully fix the issue, but it narrowed the problem and made the next debugging step clearer.

---

## Log Entry 4

**1. AI use category**  
Debugging errors, syntax / API questions

**2. What task were you trying to do?**  
I was trying to fix the `spacy`-related import issue so the preprocessing notebook would run.

**3. What prompt did you use?**  
I asked whether `spacy` was actually needed and then asked for code to verify the installed version and update it so the notebook could run.

**4. What did AI suggest?**  
AI suggested:
- checking Python and installed package versions
- upgrading `spacy` and related dependencies
- restarting the kernel after the upgrade
- verifying that `en_core_web_sm` loaded correctly

**5. What did you modify?**  
I ran the version checks and update steps, then tested the import again successfully.

**6. Why did you modify it?**  
The preprocessing notebook depended on `spacy`, so the environment needed to be fixed rather than removing it.

**7. What did you learn?**  
I learned how to troubleshoot package-version issues inside Jupyter and how kernel restarts matter after package updates.

**8. Any AI errors found?**  
No major errors. The guidance helped resolve the environment issue.

---

## Log Entry 5

**1. AI use category**  
Concept explanations

**2. What task were you trying to do?**  
I wanted to understand whether changing one file path line in `01_eda.ipynb` would affect all of the visuals and outputs.

**3. What prompt did you use?**  
I asked whether changing just the data-loading line would “change everything.”

**4. What did AI suggest?**  
AI explained that changing the file path line only changes where the notebook reads the raw CSV from and does not alter:
- the cleaning logic
- the visual generation logic
- the modeling logic

**5. What did you modify?**  
I kept the notebook logic intact and only changed the path needed to load the dataset.

**6. Why did you modify it?**  
I wanted the notebook to run on my machine without changing the substance of the analysis.

**7. What did you learn?**  
I learned how to distinguish between a portability fix and a methodological change.

**8. Any AI errors found?**  
No major errors. This was a conceptual clarification.

---

## Log Entry 6

**1. AI use category**  
Concept explanations, syntax / API questions

**2. What task were you trying to do?**  
I wanted to make the preprocessing output easier to use across notebooks and understand how to save it properly into the repo.

**3. What prompt did you use?**  
I asked where to place the processed CSV export line and whether that was the best way to share the processed data.

**4. What did AI suggest?**  
AI explained that:
- a processed CSV is a better repo-based handoff than `%store`
- it should be saved into a structured folder in the repo
- a small folder-creation step with `os.makedirs(..., exist_ok=True)` could make the export safer

**5. What did you modify?**  
I updated the output path so the processed CSV would save into a defined folder in the repo structure.

**6. Why did you modify it?**  
I wanted the notebook outputs to be organized and reusable later in the project.

**7. What did you learn?**  
I learned how to save generated notebook outputs into a structured project folder rather than leaving them in the working directory.

**8. Any AI errors found?**  
No major errors. The guidance was about workflow and file organization, not interpretation.

---

## Log Entry 7

**1. AI use category**  
Concept explanations

**2. What task were you trying to do?**  
I wanted to understand whether the NMF evaluation was still consistent with the assignment instructions, since the assignment mentioned perplexity but my NMF work used coherence and reconstruction error.

**3. What prompt did you use?**  
I pointed out the assignment’s evaluation language and asked how our NMF evaluation fit with it.

**4. What did AI suggest?**  
AI explained that:
- perplexity is generally associated with probabilistic topic models like LDA
- reconstruction error is more appropriate for matrix-factorization models like NMF
- coherence can still remain the primary metric for both
- the report should explain that LDA uses coherence + perplexity, while NMF uses coherence + reconstruction error

**5. What did you modify?**  
I adjusted my understanding of how to justify the metrics section in the report and comparison notebook.

**6. Why did you modify it?**  
I wanted to make sure the NMF evaluation could be explained honestly and in a technically defensible way.

**7. What did you learn?**  
I learned how different topic models may reasonably use different secondary evaluation metrics while still sharing coherence as the primary metric.

**8. Any AI errors found?**  
No major errors. The explanation was conceptual and helped clarify the reporting logic.

---

## Log Entry 8

**1. AI use category**  
Debugging errors, concept explanations

**2. What task were you trying to do?**  
I was trying to push my notebook work to GitHub, but I ran into a GitHub warning because the processed CSV file was too large.

**3. What prompt did you use?**  
I showed the GitHub Desktop warning and asked what I should do and whether my work would be lost.

**4. What did AI suggest?**  
AI suggested:
- do not commit the oversized CSV
- keep generated large files local
- push the notebooks and smaller repo files only
- use `.gitignore` to prevent accidentally committing the generated processed CSV and checkpoint files

**5. What did you modify?**  
I excluded the oversized CSV from the commit and used a `.gitignore` strategy.

**6. Why did you modify it?**  
I needed to protect the repo from push failures while keeping my notebook work safe.

**7. What did you learn?**  
I learned about GitHub’s file size limits and how to separate source code from large generated outputs.

**8. Any AI errors found?**  
No major errors. The guidance helped avoid a repository problem.

---

## Log Entry 9

**1. AI use category**  
Concept explanations, syntax / API questions

**2. What task were you trying to do?**  
I needed to understand what a pickle file actually is, why my loaded object did not have `.keys()`, and how to verify whether the saved pickle was valid.

**3. What prompt did you use?**  
I asked what `california_final_nmf['model']` meant, then asked how to verify the pickle file, and later asked why the loaded object did not have `.keys()`.

**4. What did AI suggest?**  
AI explained that:
- a pickle file stores a Python object in binary form
- if I saved a raw `NMF` model, loading it would return an `NMF` object, not a dictionary
- only dictionaries have `.keys()`
- to test a raw model pickle, I should inspect attributes like `n_components`, `components_.shape`, and `reconstruction_err_`
- if I wanted a richer saved object, I could instead pickle a package dictionary with branch, k, model, and feature names

**5. What did you modify?**  
I changed how I verified the pickle by inspecting model attributes instead of assuming it was a dictionary.

**6. Why did you modify it?**  
My earlier assumption about the saved object’s structure was wrong, so I needed to verify it according to what had actually been pickled.

**7. What did you learn?**  
I learned:
- what a pickle file is
- the difference between saving a raw model and saving a dictionary package
- how to verify a loaded pickle depending on the object type

**8. Any AI errors found?**  
The earlier assumption that the saved pickle would load as a dictionary did not match my actual saved file, but AI later clarified the difference and how to test the raw model properly.

---

## Log Entry 10

**1. AI use category**  
Code implementation / documentation support

**2. What task were you trying to do?**  
I needed to create a formal AI usage log for the assignment that documented only approved uses of AI from this conversation.

**3. What prompt did you use?**  
I asked AI to review the conversation and draft an AI usage log in markdown format, then later asked it to revise the log so it focused more on debugging and conceptual support rather than making it seem like AI wrote every block of code.

**4. What did AI suggest?**  
AI reorganized the conversation into approved-use entries focused on:
- debugging notebook/environment issues
- workflow and file-management concepts
- model-evaluation concepts
- pickle and repository questions

**5. What did you modify?**  
I requested a revision that removed inflated entries and shifted the emphasis toward debugging and concept clarification, which better reflected how I actually used AI.

**6. Why did you modify it?**  
I wanted the log to be accurate, honest, and appropriate for academic review.

**7. What did you learn?**  
I learned how to distinguish between acceptable AI use for technical support and prohibited AI use for topic interpretation.

**8. Any AI errors found?**  
Yes. The first draft overemphasized AI’s role in code generation, so I requested a more accurate revision.