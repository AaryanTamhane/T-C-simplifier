# 📘 Project Development Journey & Key Thinking Points

## 🧠 Critical Thinking Journey

### 1. 🧭 Defining the Problem

**Initial Problem Statement:**
Make a text summarizer for user Terms and Condition (T\&C) popups that occur on every website. Thinking from an industry-level perspective, checking condition boxes may not be that easy — by doing that, users officially grant permissions, which can be used against them in lawsuits.

**End Goal:**
Develop a Chrome extension that, when a person visits a website or service requiring acceptance of T\&C, automatically detects, extracts, and summarizes the content. It should be fast, lightweight, and eliminate the need to copy-paste text. Since users tend to skip reading T\&C within seconds, the extension must deliver a summary just as quickly.

---

## 🔍 Key Problems / Concepts / Solutions

### 1. 🧾 Where Is T\&C Text Primarily Written on Websites?

In most real-world cases, T\&C (Terms and Conditions) text is written in standard HTML, with variations:

#### ✅ 1. Plain HTML Pages – 🟢 Most Common

* Structure: T\&C is inside `<div>`, `<p>`, `<section>`, or `<article>` tags on a standalone page.
* ✅ Easy to access using `document.querySelector` or content script DOM scraping
* 🟢 Most websites follow this format

#### ✅ 2. Scroll Boxes on Signup Pages

* Structure: A modal or signup form has a scrollable `<div>` with `overflow: scroll`, containing the entire T\&C.
* ✅ Still HTML, but not fully visible unless scrolled
* 📌 Needs scroll simulation using JavaScript (`scrollTop = scrollHeight`) before extraction

**Conclusion:**
Most success comes from extracting large HTML blocks with legal language (keywords like "privacy", "terms", "agree").

📌 Your Chrome Extension content script should prioritize:

* ✅ HTML pages
* ✅ Scrollable boxes

---

### 2. 📤 Handling Long Text

**Challenge:** Large T\&C content can exceed API token limits

* ✅ Chunked content into small, semantic segments
* ✅ Used top-N chunk selection via keyword scoring (e.g., risk-related words)

---

### 3. ⚡ Optimizing Speed

**Challenge:** Existing T\&C extensions were slow

* ✅ Preprocessed text before API call
* ✅ Chose fast LLMs (e.g., GPT-4-turbo, Claude Sonnet)

---

### 4. 🤖 Choosing LLMs vs. Training Models

**Challenge:** Training with a 100-document dataset would overfit

* ✅ Shifted to zero-shot prompting using GPT-4 API for reliability and scalability

---

### 5. 🔒 Privacy Considerations

**Challenge:** How to ensure we don’t extract private or sensitive user data

* ✅ Only extract public visible text from HTML (no inputs, passwords, or hidden elements)
* ✅ Provide a disclaimer for user transparency

---

### 6. 🎨 UI/UX Design

**Challenge:** Must be non-intrusive yet informative

* ✅ Designed popup with minimal summary and quick risk indicator (color-coded: Green, Yellow, Red)

---

## 🔄 Development Workflow Summary

1. Research problem scope and study alternatives
2. Choose Chrome Extension as the delivery platform
3. Extract T\&C data using JS content scripts and DOM traversal
4. Simulate scrolling if T\&C is in scrollable boxes
5. Integrate LLM via OpenAI API for zero-shot summarization
6. Receive and display summary and risk level in popup UI
7. Optimize for UX and performance
8. Test on real sites like Instagram, Google, Spotify, etc.

---

> This journey section will continue to grow as the project matures through development milestones, feedback, and testing phases.
