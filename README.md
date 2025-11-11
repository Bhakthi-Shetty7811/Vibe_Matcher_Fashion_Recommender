## 🧾 **README — Vibe Matcher: Fashion Recommender Prototype**

### **Project Overview**

**Vibe Matcher** is a mini AI-powered fashion recommendation system that suggests outfits based on “vibes” or moods rather than explicit keywords. Given a text query like *“cozy relaxed vibe”* or *“energetic urban chic”*, the model embeds the input and matches it to fashion items with similar semantic meaning.

This prototype was designed as part of **Nexora AI Assignment**, built entirely in Colab, and ready for extension into a real AI recommendation engine.

---

### **Why AI @ Nexora?✨**

I’m drawn to Nexora’s focus on **human-centered AI** — technology that connects emotion and intelligence.
This project reflects that vision: it understands *vibes*, not just words.
It’s minimal but scalable — a starting point for building AI that feels creative and personal, not mechanical.

---

### **💻 Features Implemented**

✅ **Data Prep:**

* Created a **mock dataset of 10 fashion products** with names, descriptions, and vibe tags (e.g., `["boho", "chill"]`, `["urban", "cool"]`).
* Stored in a Pandas DataFrame for easy manipulation.

✅ **Embeddings:**

* Used `sentence-transformers/all-MiniLM-L6-v2` (Hugging Face) to generate text embeddings.  
* Originally designed for OpenAI’s `text-embedding-ada-002`, but switched due to free-tier API quota limits.  
* The notebook includes commented lines showing where to add the OpenAI API key if restored later.
* Each product’s description is encoded into a semantic vector for cosine similarity–based vibe matching.

✅ **Vector Search Simulation:**

* Used **cosine similarity** (from `sklearn`) to find products closest in meaning to a query.
* Implemented modular helper functions for clarity:

  * `compute_similarity_scores`
  * `get_top_k_matches`
  * `vibe_matcher` (main pipeline with confidence logic & timing)

✅ **Testing & Evaluation:**

* Tested 3 sample queries:

  * *“energetic urban chic”*
  * *“cozy relaxed vibe”*
  * *“vacation beach style”*
* Calculated:

  * Max & average top-3 similarity scores
  * Marked matches > 0.7 as “good”
  * Measured query latency and plotted it.

✅ **Visualization:**

* PCA 2D scatter plot of product embeddings → shows vibe clusters in 2D space.

✅ **Reflection:**

* Discussed modular design, speed, evaluation improvements, and potential future steps (FAISS/Pinecone, CLIP multimodal).

✅ **Interactive Demo (Gradio):**

* Added a **Gradio UI** that lets users type a vibe and instantly see matching fashion items in a DataFrame view.
* Fully functional when launched in Colab using:

  ```python
  ui.launch(share=True)
  ```

---

### **📈 Evaluation Summary**

| Query                | Max Sim | Avg Top-3 | Good Match?             |
| -------------------- | ------- | --------- | ----------------------- |
| energetic urban chic | 0.426   | 0.356     | ⚙️ Needs improvement    |
| cozy relaxed vibe    | 0.524   | 0.486     | ⚙️ Needs improvement    |
| vacation beach style | 0.575   | 0.449     | ⚙️ Needs improvement    |

> Current model produces weak but semantically reasonable matches — suitable for prototype stage.
> Replacing embeddings with OpenAI’s `text-embedding-ada-002` would yield better accuracy.

---

### **🧩 What’s Done vs Remaining**

| Task Area                             | Status                       | Notes                                                                |
| ------------------------------------- | ---------------------------- | -------------------------------------------------------------------- |
| **Data Prep (5–10 mock products)**    | ✅ Done                       | 10 well-labeled fashion items                                        |
| **Embeddings (OpenAI)**               | ⚠️ Replaced with MiniLM      | Used local transformer instead of OpenAI for free, reproducible runs |
| **Vector Search (Cosine Similarity)** | ✅ Done                       | Top-3 matches with confidence thresholds                             |
| **Test & Evaluation**                 | ✅ Done                       | 3 test queries, latency graph, average metrics                       |
| **Reflection (3–5 bullets)**          | ✅ Done                       | Clear, concise self-evaluation                                       |
| **Gradio Prototype UI**               | ✅ Added                      | Optional extension for real-time vibe search                         |
| **Notebook Formatting / Outputs**     | ✅ Done                       | All outputs visible and explained                                    |
| **GitHub Render Validation**          | ✅ Fixed (no widget metadata) | Safe for submission                                                  |

---

### **🪄 Future Enhancements**

* Use **OpenAI embeddings** for higher semantic precision.
* Plug into a **vector database** (FAISS or Pinecone) for scalability.
* Combine **text + image embeddings (CLIP)** for a true multimodal “Vibe Matcher”.
* Add user feedback loop (like/dislike → model fine-tuning).

---

### **🧍‍♀️ Author**

**Bhakthi Shetty**
