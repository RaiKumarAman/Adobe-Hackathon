# Round 1B: PDF Subsection Analysis - Process Description

## Objective
The goal of this solution is to identify and summarize the most relevant sections from a set of PDF documents, based on a given **persona** and a specific **job to be done**. This is done through a multi-step pipeline that extracts, ranks, and summarizes text content from each document.

---

## Process Overview

### 1. Input Preparation
- All PDF documents are placed inside an `input/` folder.
- A JSON file named `persona_task.json` is provided, containing:
  - `persona`: the role or profile of the user (e.g., a policy analyst).
  - `job_to_be_done`: the specific task or goal they are trying to accomplish (e.g., extract rural healthcare insights).

---

### 2. Text Extraction & Segmentation
- Each PDF is read and segmented into logical sections or paragraphs.
- For each segment, metadata such as the document name and page number is recorded.
- The text is cleaned and structured into a list of sections.

---

### 3. Relevance Ranking
- Each extracted section is scored for its relevance to the given persona and job.
- A ranking model (rule-based or LLM-based) determines which sections are most likely to help the persona accomplish their goal.
- The top N sections (e.g., top 5) are selected based on these scores.

---

### 4. Summarization
- The selected top-ranked sections are then passed through a summarization process.
- Summaries are generated to concisely represent the key points of each section.
- The summaries are contextualized with metadata: document name, page number, and original text.

---

### 5. Output Generation
- A final JSON output is created containing:
  - Metadata (persona, job, timestamp, document names).
  - A ranked list of important sections.
  - Summaries of each top-ranked section.
- This output serves as a compact and targeted insight report tailored to the persona's needs.

---

## Outcome
The final result is a structured JSON file containing only the most relevant and summarized information from a large corpus of PDFs—streamlining the research or decision-making process for the specified persona.

