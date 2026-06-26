# &#x20;LexiGuard AI - Multi-Agent Legal Compliance System

A sophisticated, multi-agent LLM application built with Gemini 2.5 Flash for intelligent legal document analysis, risk assessment, and contract negotiation.



## 📋 Table of Contents

* Project Overview
* Key Features
* Architecture
* Technical Stack
* Usage Guide
* Agent Personas
* Core Functionality
* Testing Your System
* Troubleshooting
* Project Structure
* Future Enhancements
* Credits



### 🎯 Project Overview

LexiGuard AI is a single-file HTML application that demonstrates advanced LLM capabilities through a multi-agent legal compliance system. Built for a university workshop, it showcases:



* Multi-Agent Architecture - Three specialized legal agents
* Retrieval-Augmented Generation (RAG) - Document-aware responses
* Agentic Reasoning - Dynamic decision-making based on context
* Visual Analytics - Risk heatmaps and deadline extraction
* IO Minimalist Design - Swiss-style UI with dark mode



#### The Problem We Solve

Legal professionals spend hours searching through thousands of pages of contracts, compliance documents, and regulations. LexiGuard AI provides an intelligent assistant that can:



* Answer questions with page-specific citations
* Identify risky clauses and legal vulnerabilities
* Rewrite unfair terms with balanced alternatives
* Extract deadlines and obligations into structured tables
* Generate visual risk assessments



### ✨ Key Features



1. ##### Multi-Agent Chatbot System

|Agent|Role|Persona|
|-|-|-|
|Lexi|Compliance Sentinel|Answers questions with citations, identifies contradictions|
|Judge|Litigation Advocate|Devil's advocate, finds ambiguities \& unfair terms|
|Dealmaker|Negotiator|Rewrites bad clauses, suggests fair counter-offers|

&#x09;

##### 2\. Document Management ("The Vault")

* Drag-and-drop upload (PDF, TXT, MD, HTML, CSV)
* Multi-document selection
* Document viewer with extracted text
* Select All functionality for batch analysis



##### 3\. Smart Workspace

* Split Viewer: Document text + Analysis Dashboard
* Extract Deadlines: Generates structured tables of obligations, responsible parties, deadlines, and penalties
* Risk Heatmap: Visual color-coded risk assessment (🟢 Low, 🟡 Medium, 🔴 High) across Privacy, Security, Liability, and Compliance



##### 4\. Advanced LLM Capabilities

* RAG (Retrieval-Augmented Generation): Answers based on uploaded documents
* Agentic Nature: Detects when queries are general knowledge vs. document-specific
* Conflict Detection: Alerts when documents contain contradictory clauses
* Page Citations: Every response references specific pages and sections



##### 5\. IO Minimalist Design

* Dark Mode Toggle with smooth transitions
* Glowing API Status Indicator (pulses green when connected)
* Swiss-style typography with Inter and JetBrains Mono fonts
* Minimalist tables with alternating row colors



### 🏗️ Architecture



┌─────────────────────────────────────────────────────────────┐

│                                LexiGuard AI                                     │

├─────────────────────────────────────────────────────────────┤

│                                                                                 │

│  ┌──────────────┐  ┌──────────────┐  ┌──────────────────┐      │

│  │   The Vault      │  │   Workspace       │  │  Multi-Agent Chat      │      │

│  │  (Sidebar)       │  │  (Center)         │  │   (Right Panel)        │      │

│  │                  │  │                   │  │                        │      │

│  │ 📄 Upload        │  │ 📄 Document      │  │ 🧑‍⚖️ Lexi                │     │

│  │ 📂 File List     │  │ 📊 Dashboard     │  │ ⚖️ Judge               │     │

│  │ ☑️ Selection     │  │ 🔍 Analysis      │  │ 🤝 Dealmaker           │     │

│  └──────────────┘  └──────────────┘  └──────────────────┘      │

│                                                                                 │

│  ┌─────────────────────────────────────────────────────────┐ │

│  │              API Key Footer + Status                                       │ │

│  │  🔌 Connected (In-Memory Session)                                         │  │

│  └─────────────────────────────────────────────────────────┘ │

└─────────────────────────────────────────────────────────────┘



### 🛠️ Technical Stack

|Layer|Technology|
|-|-|
|Frontend|Vanilla HTML + CSS + JavaScript|
|Styling|Tailwind CSS (via CDN) + Custom CSS|
|Icons|Lucide Icons|
|PDF Processing|PDF.js v3.11.174|
|LLM API|Google Gemini 2.5 Flash|
|Design Philosophy|IO Minimalism (Swiss Style)|
|Dependencies|None - Single HTML File|



#### Model Details

* Primary Model: gemini-2.5-flash
* System Instructions: Custom prompts per agent



### 📖 Usage Guide



#### Step-by-Step Walkthrough



##### 1\. Upload Documents



Drag \& drop → "The Vault" sidebar

OR

Click drop zone → Select files



Supported formats: PDF, TXT, MD, HTML, CSV



##### 2\. Select Documents

* Click checkbox next to each document to select it
* Use "Select All" for batch analysis
* Click document title to view in Workspace



##### 3\. Choose Your Agent



Switch between three specialized agents via tabs:

|Tab|Use Case|
|-|-|
|Lexi|"What are the compliance requirements?"|
|Judge|"Find risky or ambiguous clauses."|
|Dealmaker|"Rewrite this unfair clause."|

&#x09;

##### 4\. Ask Questions



Example queries:

* "What is the completion deadline for this contract?"
* "Identify any ambiguous terms in Section 2.9."
* "Rewrite the liquidated damages clause to be fairer."
* "What are the payment terms in this agreement?"



##### 5\. Use Advanced Features



📅 Extract Deadlines



Click "Extract Deadlines" → Generates a table like:



|Obligation|Responsible Party|Deadline|Penalty for Late|
|-|-|-|-|
|Complete Work|Contractor|90 days|$250/day|



📊 Risk Heatmap



Click "Risk Heatmap" → Generates:



|Area|Risk Level|Specific Violation|
|-|-|-|
|Privacy|🟢 Low|No sensitive data|
|Liability|🔴 High|Broad indemnification|



### 👥 Agent Personas



🧑‍⚖️ Lexi - Compliance Sentinel



Role: Standard RAG agent

Focus: Document retrieval, clause extraction, contradiction detection

Personality: Professional, precise, citation-focused

System Prompt:



"You are Lexi, a compliance expert. Always cite page numbers or sections. First, decide if the query is 'Document-Specific' or 'General Knowledge'. If general knowledge, answer freely. If Document-Specific, use the provided context. Crucially: If you find contradictory clauses in two different uploaded docs, alert the user immediately with: '⚠️ Conflict Detected: \[Doc A] says X, but \[Doc B] says Y.'"



⚖️ Judge - Litigation Advocate



Role: Devil's Advocate

Focus: Identifying legal vulnerabilities, ambiguities, and unfair terms

Personality: Critical, skeptical, adversarial

System Prompt:



"You are a Litigation Judge acting as a Devil's Advocate. Identify contract vulnerabilities, ambiguous language, unfair terms, and clauses that could be challenged in court. Be highly critical and adversarial. Example format: '⚠️ Warning: This contract does not define 'Force Majeure' clearly. A judge would likely rule against the drafter in a dispute.'"



🤝 Dealmaker - Negotiator



Role: Contract Improver

Focus: Rewriting problematic clauses, suggesting counter-offers

Personality: Diplomatic, practical, constructive

System Prompt:



"You are a Negotiator Agent (Dealmaker). Your goal is to rewrite problematic, ambiguous, or 'bad' clauses into balanced, 'fair' clauses. Provide counter-offer suggestions in plain English. For every change, briefly explain why the original was problematic and why your rewrite is fairer for both parties."



### 🎯 Core Functionality



#### RAG (Retrieval-Augmented Generation)

1. User uploads documents to "The Vault"
2. Documents are stored in memory with extracted text
3. Selected documents are included in the context
4. LLM answers based on document content + general knowledge



#### Agentic Decision Making

If user query is document-specific:

&#x20;   → Search documents → Provide answer with citations



Else if user query is general knowledge:

&#x20;   → Answer directly from LLM knowledge



Else if documents contain contradictions:

&#x20;   → Flag conflict with warning



#### Citation System

* Every response includes source references
* Clicking citations highlights the clause in the document viewer
* Format: \[Source: DocumentName.pdf, Page X, Paragraph Y]



#### Visual Analytics

Deadline Extraction:

Input: Construction contract with dates

Output: HTML table with obligations, responsible parties, deadlines, penalties



Risk Heatmap:

Input: Legal document

Output: 4x2 table with Privacy, Security, Liability, Compliance risk levels



### 🧪 Testing Your System



#### Test Documents



Best Document for Full Testing:

"A - Sample Construction Agreement" - Contains deadlines (90 days), penalties ($250/day), insurance requirements, and compliance clauses



Downloaded from: Greenville County Procurement Portal



##### Test Queries

|Agent|Query|Expected Output|
|-|-|-|
|Lexi|"What is the completion deadline?"|"90 calendar days from Notice to Proceed"|
|Judge|"Find risky clauses."|"⚠️ Section 2.9 has broad indemnification"|
|Dealmaker|"Rewrite the liquidated damages clause."|"Proposed: $250/day, capped at 10% of contract value"|



##### Test Sequence

1. Upload Sample Agreement
2. Click Extract Deadlines → Should show 90 days, $250/day
3. Click Risk Heatmap → Should show all 4 categories
4. Ask Lexi: "Summarize the contract."
5. Ask Judge: "What are the risks?"
6. Ask Dealmaker: "Rewrite the indemnification clause."



### 🐛 Troubleshooting



#### Common Issues \& Fixes

|Issue|Solution|
|-|-|
|"Model not found" error|Change model to gemini-2.5-flash (not preview version)|
|Invalid JSON payload error|Remove display and family fields from API request|
|PDF shows gibberish|PDF.js not loaded - add CDN script or use text files|
|API key not connecting|Check key starts with AIza... and has no spaces|
|Heatmap shows only one category|Update prompt to explicitly request ALL FOUR categories|
|Chat not responding|Check API key, refresh page, re-enter key|



### 🚀 Future Enhancements



### Planned Features



1. Multi-Document Comparison
* Side-by-side clause comparison
* Automated redlining



2\. Export Capabilities

* PDF report generation
* CSV export of deadlines
* Save chat history



3\. Agent Collaboration

* "Ask All Agents" button
* Multi-agent consensus



4\. Advanced Analytics

* Contract score (0-100)
* Benchmark against industry standards



5\. Extended File Support

* DOCX, XLSX parsing
* Image OCR (scanned contracts)



### 📚 Credits



#### Technologies

Google Gemini API - LLM provider

PDF.js - PDF text extraction

Tailwind CSS - Utility-first styling

Lucide Icons - Icon library

Inter \& JetBrains Mono - Typography



#### Team

Built for: Build with AI Agent Builder Camp, organized by GeeksforGeeks in collaboration with Google for Developers

Architecture inspired by multi-agent AI systems

Design philosophy: IO Minimalism (Swiss Style)



#### Special Thanks

Sir Ashish Jangra for project guidance

Google AI Studio for free API access

Greenville County for sample contracts



#### License

This project is created for educational purposes as part of a the Google Build with AI LIVE workshop. Feel free to use and modify for learning purposes.

