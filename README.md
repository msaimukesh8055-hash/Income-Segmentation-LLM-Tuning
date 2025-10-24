# Text Classification with Gemini (LLM Tuning) — Income Segmentation

### 1. Project Overview  
Tuned **Gemini** in Vertex AI Studio to classify households into **Low / Medium / High** income bands from profile attributes. The tuned model serves instant classifications via an endpoint, replacing slow, manual segmentation.

### 2. Business Problem  
- **Pain Point:** Income segmentation is often done in Excel/SQL with static rules; it’s slow, inconsistent across analysts, and hard to maintain.  
- **Existing Methods:** Hand-crafted thresholds and lookups that require frequent manual updates and don’t generalize across regions or channels.  
- **Opportunity:** An LLM-tuned classifier that adapts to patterns in historical data and provides **consistent, real-time** segmentation for marketing, credit, and personalization.

### 3. Solution  
- **Tools Used:** Vertex AI Studio (LLM Tuning), Gemini (1.5/2.x), Cloud Storage/BigQuery for labeled data, Vertex AI Endpoints, Cloud Shell for quick tests.  
- **Workflow:**  
  1) **Prepare labeled dataset** (features → `Low/Medium/High`).  
  2) **Import to Vertex AI Studio → Tuning** and choose **Classification**.  
  3) **Fine Tuning**: Vertex handles data split, optimization, checkpoints, and metrics (Accuracy/Loss).  
  4) **Evaluate** in Studio; pick the best checkpoint.  
  5) **Deploy** tuned model to a **Vertex AI endpoint**.  
  6) **Infer** via prompt/API to classify new households in real time.  
- **Automation Highlights:** Vertex automates data split, training loops, and hyper-parameter search; Studio provides built-in evaluation and one-click deployment.

### 4. Input and Output Example

**Input (prompt to tuned model):**
```text
Classify the household into Low, Medium, or High income.

Age: 56
Income: 29330
Years exp: 27
Credit scrore: 431
Gender: male
Location: suburban

Can you suggest the class as per above data
```

**Output
```
Low income category
```

### 5.Business Impact:
- ~50% reduction in manual segmentation effort vs. Excel/SQL rules; teams use a single API for consistent labels across channels.
- Scalable & consistent classifications for thousands of records per second; improves targeting, reduces bias, and accelerates decisioning in CRM/credit workflows.

### 6. Real-World Applications
- **Banking & Credit Scoring:** Rapid household income classification to pre-qualify loan applications or credit card offers at scale.
- **Retail & E-commerce:** Dynamic segmentation of customer bases into income tiers for personalized promotions, loyalty programs, and product recommendations.

### 7. Screenshots [Text classification.pdf](https://github.com/user-attachments/files/23122585/Text.classification.pdf)
