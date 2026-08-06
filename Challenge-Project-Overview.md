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
This project focuses on modernizing document-processing workflows for organizations that handle high volumes of unstructured physical or digital files. By leveraging advanced multimodal AI, the team aims to replace manual data entry tasks with automated classification and structured extraction pipelines.

---

## 🎯 The Challenge
### Project Summary
The team will design and implement a multimodal pipeline using ColPali and ColQwen2 to categorize business documents and extract key information into structured JSON formats. This project utilizes a public benchmark dataset to compare embedding architectures and evaluate their effectiveness in clustering and classification, directly addressing the bottleneck of manual document handling.

### Success Criteria
Embedding comparison: clear head-to-head of ColPali vs. ColQwen2. Clustering: silhouette, Davies-Bouldin, ARI/NMI metrics. Classification: accuracy, macro-F1, confusion matrix. Extraction: field-level accuracy/F1 and JSON validity.

### Project Milestones
Use these milestones to guide your work. Your team will create a GitHub Projects board to track tasks within each milestone.

| Month | Milestone | Key Activities |
| :--- | :--- | :--- |
| September | Data Setup, Preprocessing & Text Baseline | • Ingest and inspect the multimodal document dataset (images, OCR text, document layout annotations).<br>• Clean text OCR outputs and standardize document image dimensions.<br>• Implement baseline text-only embeddings (TF-IDF / Sentence-Transformers) for document classification.<br>• Establish evaluation metrics (Accuracy, Macro F1-score, Extraction Precision/Recall). |
| October | Multimodal Embedding Extraction & Comparison | • Extract visual and layout-aware embeddings using pre-trained vision-language models (e.g., CLIP, LayoutLM, ColPali, or SigLIP).<br>• Train classification heads and entity extraction pipelines on candidate embedding representations.<br>• Conduct comparative benchmarking between text-only, visual, and joint multimodal embeddings across document types. |
| November / December | Model Evaluation, Interactive UI & Deliverables | • Perform error analysis on challenging document categories (e.g., multi-column layouts, noisy scans, tabular structures).<br>• Build an interactive Streamlit application to upload document images, visualize embedding features, and compare extraction outputs.<br>• Package a clean, reproducible GitHub repository, project documentation, and final presentation deck. |

### Stretch Goals
* **Domain-Specific Fine-Tuning:** Fine-tune a lightweight multimodal encoder on specialized document classes (e.g., financial receipts, medical intake forms) to improve key-value extraction precision.
* **Interactive Bounding Box Visualizer:** Build an overlay feature in the UI that displays extracted entity fields and bounding boxes directly over the original document images.
* **Zero-Shot Layout Generalization:** Benchmark zero-shot transfer performance of multimodal embeddings on completely unseen document formats or non-English document layouts.
> **Note for the team:** Please create a GitHub Projects board in this repository to break these milestones into weekly tasks. Go to the **Projects** tab → **New project** → Choose **Board** → Add columns for each month.

---

## 📊 Dataset
**Name and Source:** [OCR-Benchmark Dataset](https://huggingface.co/datasets/getomni-ai/ocr-benchmark)  
**Format:** JSON, Images, Text  
**Size:** 1gb to 5gb  
**Location:** https://huggingface.co/datasets/getomni-ai/ocr-benchmark  

### Key Details
- Publicly available dataset of business document images, text, and categorical data (JSON, image files). 
- The team must ensure strict handling of outlier document formats and maintain consistency in JSON schema mapping during extraction to avoid parsing errors.

---

## 🛠️ Suggested Approach
**ML Problem Type:** NLP & RAG / Classification  
**Recommended Libraries:**
- ColPali, ColQwen2, OCR, PCA, UMAP, t-SNE, logistic regression, k-NN, random forest, multimodal LLM, JSON
**Evaluation Metrics:** Embedding quality (Silhouette/Davies-Bouldin), Classification accuracy/F1-score, and JSON schema field-level extraction validity.

---

## 📚 Resources to Get Started
The following resources will help your team understand the problem space and potential technical approaches for this project:
**Background Reading:**
- Research on multimodal embedding architectures for document retrieval.
**Technical Tutorials:**
- Documentation for Hugging Face Transformers and the specific ColPali implementation libraries.
**Code Examples:**
- Sample multimodal inference notebooks provided via standard Hugging Face/GitHub documentation for vision-language models.

---

## 🤝 How We'll Work Together
**Check-ins:** During our biweekly 60-min AI Studio Lab Section meeting block (2nd and 4th week of every month)  
**Communication:** Email and scheduled Lab Section syncs.  
**Response time:** 48 hours for non-urgent technical queries.  
**Recommended Tools:**
- **Coding:** Google Colab Free Tier  
- **Collaboration:** GitHub, Notion  
- **Virtual Meetings:** Zoom, Google Meet  

---

## 🚀 Getting Started
1. **Review this overview document** and note any questions for our first meeting.
2. **Begin reviewing the dataset** using the link provided in the Dataset section.
3. **Read the GitHub Projects documentation** [here](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects).

I'm excited to work with you!

---

## ❓ Questions?
Please bring any questions to our first meeting during the week of August 24th (Break Through Tech's Bridge to Studio - Session B).
