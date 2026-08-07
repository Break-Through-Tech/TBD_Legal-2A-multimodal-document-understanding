---

> ## Challenge Advisor: Update & Finalize Your Project Overview
>
> > 💡 **These grey text instructions are just for you, the team's Challenge Advisor; please delete them once you have completed the steps below.**
>
> We've pre-populated this Challenge Project Overview page — which is what will be shared with your Break Through Tech student team in August — using the details from your submission form. You should have received an email inviting you to join this repo as a Collaborator, enabling you to add files and make edits.
> 
> In order for your project to be finalized and assigned to a team, please:
> 1. **Review all sections below** and update or expand any content as needed, making sure to address the SME Feedback in the section immediately below. Look for square brackets to find the places below that require additional inputs from you (e.g., "About [Company / Org Name]").
> 2. **Add your dataset** to the [data folder](data) in this repo.
> 3. **Close the Issue assigned to you in this repo** to let us know that you have made your edits and the overview page is ready for final review. You can do this by going to the _Issues_ tab in the top left section of the menu above, add a comment that says "CA review complete", and click the button to Close the Issue. 
>
> If you're unfamiliar with how to edit a page like this in GitHub, check out [this tutorial](https://ubc-lib-geo.github.io/gis-workshop-waml-template/content/handson/edit-readme.html) for a quick overview (start with step 2 and only edit this page), and [this guide](https://ubc-lib-geo.github.io/gis-workshop-waml-template/content/markdown.html) on how to use Markdown to compose text.
>
>
> ❌ Remember that this is a public repo. Do NOT include: Proprietary data, PII, API keys, credentials, or anything confidential.

---

## 📋 BTT Internal Evaluation Notes
*(This section is for BTT staff and CAs only — remove before sharing with students)*

### Technical Vetting
| Check | Status | Notes |
| :--- | :--- | :--- |
| Python Compatibility | 🟢 | Stack utilizes standard libraries like scikit-learn and transformers, but ColPali/ColQwen2 architectures require significant RAM, which may hit free-tier Colab limits. |
| Data Readiness | 🟢 | Dataset is well-structured and available on Hugging Face, reducing time spent on initial collection. |
| Resource Check | 🟡 | ColPali and multimodal LLMs are compute-intensive; inference on the free Colab tier may be sluggish or prone to OOM errors during batch processing. |

### Internal Scores
- **Student Fit Score:** 6.5/10
- **Technical Depth Score:** 8/10
- **Overall Recommendation:** REVISE

### Advisor Feedback Draft
The proposal provides a compelling look into current document-processing workflows. To ensure success, focus on optimizing inference batch sizes to avoid memory limits in Colab, and establish a strict deterministic validation protocol for the JSON extraction phase rather than relying solely on LLM output. I recommend prioritizing a robust evaluation framework over model architecture variety to ensure the project remains achievable within the 12-week timeframe.

---

# Multimodal Document Understanding: Comparing Embeddings for Classification and Extraction

**Company / Org:** Other  
**Challenge Advisor:** Grace Lang, graceelang@gmail.com  
**AI Studio Coach:** Hrushikesh Shetty, hrushikesh.shetty@breakthroughtech.org  
**Program:** Break Through Tech AI Studio - Fall 2026  

---

## 🏢 About Other
[TBD]

---

## 🎯 The Challenge
### Project Summary
In this project, you will use a public benchmark of business document images and multimodal embedding models, clustering, classification, and an open-source multimodal LLM to build a pipeline that sorts documents by type and extracts their structured data. This will help our company address the costly, manual work of processing high volumes of unstructured documents.

### Success Criteria

Success is measured per stage, against the dataset's built-in ground truth

- Embedding comparison: a clear, quantitative head-to-head of ColPali vs. ColQwen2 (vs. OCR-text) on how well each separates document types, with a justified recommendation.   
- Clustering: cluster-quality metrics (silhouette, Davies–Bouldin) and agreement with true labels (ARI / NMI) across at least three algorithms.   
- Classification: accuracy, macro-F1, and confusion-matrix analysis on a held-out test set, with a documented baseline and at least one improvement on it.   
- Extraction: field-level accuracy / F1 and JSON validity of the multimodal LLM's output, measured against the ground-truth structured answers, plus an error analysis.   

A successful December outcome: a working end-to-end pipeline (embed → cluster/classify → flag unknown types → extract structured data), a clear answer to the ColPali-vs-ColQwen2 question backed by metrics, a public, reproducible GitHub repository, and a final presentation

### Stretch Goal
Agentic IDP router: a tool-calling agent that classifies an incoming document, flags unknown types for human review, routes recognized types to the correct extraction schema, and validates the extracted JSON.

### Project Milestones
Use these milestones to guide your work. Your team will create a GitHub Projects board to track tasks within each milestone.

| Month | Milestone | Key Activities |
|---|---|---|
| September | Embeddings, the ColPali vs. ColQwen2 comparison, clustering | • Embed every document with ColPali and ColQwen2; cache the vectors.<br>• Build a third embedding channel from OCR text.<br>• Visualize each embedding space with PCA / UMAP / t-SNE.<br>• Compare at least three clustering algorithms against the true type labels (ARI / NMI, silhouette).<br>• Deliver the head-to-head verdict: which embedding best separates document types |
| October | Classification & the new-type problem | • Train classifiers (logistic regression, k-NN, random forest; optional neural head) to predict document type.<br>• Run model selection; report accuracy, macro-F1, and a confusion-matrix analysis.<br>• Hold out one document type during training to simulate a never-before-seen class.<br>• Build and evaluate a novelty / out-of-distribution detector that flags the unknown type |
| November | Multimodal LLM extraction & evaluation | • Prompt an open-source multimodal LLM to extract structured JSON using each document's schema.<br>• Score extractions against the ground-truth answers (field-level accuracy / F1, JSON validity).<br>• Run an error analysis of failure modes (low-quality scans, complex tables, hallucinated fields). |

> **Note for the team:** Please create a GitHub Projects board in this repository to break these milestones into weekly tasks. Go to the **Projects** tab → **New project** → Choose **Board** → Add columns for each month.

---

## 📊 Dataset
**Name and Source:** OCR-Benchmark Dataset
**Format:** JSON, Images, Text  
**Size:** 1gb to 5gb  
**Location:** https://huggingface.co/datasets/getomni-ai/ocr-benchmark 

### Key Details
- [Brief description of what's in the data]
- [Any known limitations or preprocessing needed]
- [Link to data dictionary or documentation, if available]
  
---

## 🛠️ Suggested Approach

**ML Problem Type:** Classification, Clustering, NLP, Computer Vision, Deep Learning / Neural Networks, LLMs/ Generative AI, Transfer Learning / Pre-trained Models

**Recommended Libraries:**
- [e.g., pandas, scikit-learn, TensorFlow, Hugging Face]

**Evaluation Metrics:**
- [e.g., Accuracy, Precision/Recall, RMSE, BLEU score]
  
---

## 📚 Resources to Get Started

The following resources will help your team understand the problem space and potential technical approaches for this project:

**Background Reading:**
- [e.g., Link to an article or blog post about the problem domain]
- [e.g., Link to an industry report or case study]

**Technical Tutorials:**
- [e.g., Link to a free tutorial on the ML technique(s) involved]
- [e.g., Link to documentation for a key library or tool]

**Code Examples:**
- [e.g., Link to a relevant GitHub repo]
- [e.g., Link to a sample implementation or starter code]

**Other:**
- [Links to any additional resources — e.g., papers, videos, podcasts, etc.]

*Feel free to explore beyond these, and share anything interesting you find with me!*

---

## 🤝 How We'll Work Together

**Official check-ins:** During our biweekly 45-minute AI Studio Lab Section meeting block (2nd and 4th week of every month)

 **Other ways to reach out to me with questions:** 
* [e.g., Your team's channel within Break Through Tech’s Discord space]
* [e.g., Email; please copy your teammates and AI Studio Coach]
* [e.g., Request a team check-in on Zoom]
* [Note: I will aim to respond within 48 hours. Please reach out to your AI Studio Coach with urgent questions.]

> 💡 **Challenge Advisor: Please update the above based on your availability and preference. If you are not able to answer questions or meet with fellows outside of the biweekly Lab Section check-ins, simply write in "N/A (only available during the official check-in times)"**

**Recommended free coding / collaboration tools**
* […]
* […]

---

## 🚀 Getting Started

1. **Review this overview document** and note any questions for our first meeting
2. **Begin reviewing the dataset** using the link above
3. **Read the GitHub Projects documentation** [here](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects)

I’m excited to work with you!

---

## ❓ Questions?

Please bring any questions to our first meeting during the week of August 24th (Break Through Tech’s Bridge to Studio - Session C). 
