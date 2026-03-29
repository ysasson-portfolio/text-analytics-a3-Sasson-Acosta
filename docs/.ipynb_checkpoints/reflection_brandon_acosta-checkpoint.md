# Reflection — Brandon Acosta

## Overview

This project gave me a much better understanding of how topic modeling works in practice, especially when comparing multiple models across separate groups within the same dataset. Our team used Disneyland reviews and split the analysis across California, Paris, and Hong Kong, which made the project more interesting because it was not just about building one model, but about comparing patterns across locations.

From the start, the project felt very applied. There was a technical side, which involved preprocessing, matrix construction, model fitting, evaluation, and visualization, but there was also a collaborative side that required dividing responsibilities clearly and keeping our GitHub workflow organized. I was responsible for the NMF side of the project, while Yarden handled the LDA side. That split worked well because it gave each of us clear ownership over one modeling approach while still leaving room for collaboration on the shared parts of the assignment.

## What I Learned

The biggest thing I learned was how different topic modeling methods require different inputs and different ways of thinking about evaluation. Before this assignment, I understood topic modeling more generally, but I had not worked through the full process of building branch-specific inputs, testing multiple values of `k`, comparing metrics, and organizing the outputs in a way that would later support human interpretation.

On the technical side, I learned a lot about the NMF workflow. In particular, I learned:
- how to build separate TF-IDF matrices for different groups in the same dataset
- how to structure a reusable loop for testing multiple topic counts
- how to compare coherence and reconstruction error across topic counts
- how to extract top words and top documents from the final model
- how to generate visuals such as topic word clouds and average topic distribution plots

I also learned that topic modeling projects are not just about getting a model to run. A large part of the work is making the outputs usable for interpretation later. Printing top words, saving representative documents, organizing visuals, and exporting files in a clean repo structure all matter because they make the next stage of the project much easier.

I also learned more about practical notebook workflow issues. Getting the notebooks to run across devices, working with relative file paths, understanding what `%store` does and does not do, and deciding what should or should not be pushed to GitHub were all small but important lessons. Those issues are easy to overlook, but they affect whether a shared project actually works.

## Challenges

The biggest challenge for me was not the NMF model itself, but the environment and workflow issues around the project. Since parts of the notebook structure had originally been set up on a different machine, I had to work through path issues, package import issues, and output-file organization in order to get the workflow running smoothly on my end.

One challenge was making sure the notebooks were still aligned with my groupmate’s work while also being usable in the shared repository. I wanted to avoid unnecessarily changing work that had already been built, especially in the early notebooks, but I also needed the pipeline to run correctly on my machine. That meant being careful about what to adjust and what to leave alone.

Another challenge was making sure my NMF notebook matched the style and expectations of the professor’s example notebook. Even when code is technically correct, presentation and structure matter in a class setting. I spent time making sure the TF-IDF setup, NMF configuration, evaluation flow, and saved outputs were consistent with what had been demonstrated in class.

A final challenge was the distinction between technical modeling and interpretation. Since the assignment was strict about interpretation being completed without AI, it was important to keep the technical notebook focused on model outputs and save the actual naming and interpretation of topics for the later shared interpretation work.

## Reflection on the Pair Process

Overall, I think our pair structure worked well because the responsibilities were clear. We each had a distinct model to own, which reduced confusion and made it easier to divide the technical work in a fair way. Yarden handled the LDA side and much of the original setup for the EDA and preprocessing notebooks, while I focused on the NMF modeling, evaluation, outputs, and visuals.

I appreciated that there was enough independence in the assignment for each person to take ownership over a major section, while still leaving room for collaboration in the comparison and interpretation stages. That balance made the work feel more manageable.

At the same time, this project also showed that shared notebook projects require strong coordination, especially when one student builds part of the pipeline first. Even small issues like file paths, generated outputs, or package compatibility can become collaboration issues if they are not standardized. In future projects, I would try to establish shared repo conventions even earlier, especially for:
- relative file paths
- output folders
- generated files that should stay local
- files that should be committed vs ignored

That would make the handoff between teammates smoother.

## Peer Evaluation — Yarden Sasson

Yarden contributed strongly to the project by establishing the earlier notebook workflow and taking ownership of the LDA model. He handled the original EDA and preprocessing setup, which gave the project a strong starting point and made it possible to divide the modeling work more efficiently later.

He also contributed by keeping the project moving forward on his side of the model implementation. Since the project required two different topic-modeling approaches, having clear model ownership helped prevent overlap and made the division of labor more practical.

One strength of Yarden’s contribution was providing the original notebook structure and getting the project pipeline started. That made it easier for me to focus on building out the NMF side rather than starting the project from scratch.

Overall, I believe Yarden contributed meaningfully to the project and completed his side of the technical work. The division of responsibilities was clear, and the collaboration was productive.

## Final Takeaway

This project helped me feel much more comfortable with the end-to-end workflow of unsupervised text analysis. I came away with a stronger understanding of:
- how to structure topic modeling notebooks
- how to evaluate and compare models
- how to organize outputs for later interpretation
- how to manage collaboration in a notebook-based GitHub project

The project also reinforced that successful analytics work is not only about building a model. It is also about making the workflow reproducible, making the outputs interpretable, and working effectively with another person to produce a final result that is organized and defensible.