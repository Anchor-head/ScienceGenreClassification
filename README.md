# Science Genre Classification
This project consists of labelling articles from Science the journal according to the following genre schema:

<img width="600" alt="image" src="https://github.com/user-attachments/assets/35012ac8-00e0-42e3-a4bf-ca9214aa568c" />

For this task, a pre-trained SciBERT-based sentence transformer is be fine-tuned and trained with a classification head, with pre-classification sentence embeddings augmented by article metadata.

Two training flows are experimented with to compensate for the scarcity of manually labelled data:
1. A teacher-student model whereby a pre-trained LLM (such as GPT-4.1) is leveraged to label enough data to train the sentence transformer on.
2. SetFit, a contrastive learning framework whereby the sentence transformer is first fine-tuned as a siamese network before the classification head is added and trained on the classification task directly.

[This google doc](https://docs.google.com/document/d/1iaJYEF_OVMhJenAl9A5wKH2dS4ZrcwuOyoX3Tjxpc44/edit?tab=t.0#heading=h.e694d1lypnpl) contains a more detailed description of the project's workflow.

## Scripts
SetFit-SciBERT.ipynb is a jupyter notebook developed on Google Colab to train a sentence transformer using SetFit.
