# <div align="center"> 💧✨ Gamma AI Watermark Remover ✨💧 </div>
<div align="center">
  <img src="https://img.shields.io/badge/Python-3.7+-blue.svg?style=flat-square&logo=python&logoColor=white" alt="Python Version">
  <img src="https://img.shields.io/badge/Quart-0.18+-brightgreen.svg?style=flat-square&logo=python&logoColor=white" alt="Quart">
  <img src="https://img.shields.io/badge/fitz-1.18+-orange.svg?style=flat-square&logo=python&logoColor=white" alt="PyMuPDF (fitz)">
  <img src="https://img.shields.io/badge/PIL-9.0+-yellow.svg?style=flat-square&logo=python&logoColor=white" alt="Pillow (PIL)">
</div>
<div align="center">
  <p> ⚠️ <b>Educational Purposes Only</b> ⚠️ </p>
</div>

<br/>

<p align="center">
  <b>Remove those Gamma AI Watermarks! 🚀 Effortlessly clean up your PDFs generated by Gamma AI's free tier.</b>
</p>

<br/>

---

## 🌟 What is Gamma AI Watermark Remover?

Created presentations with Gamma AI and now have unwanted watermarks on your PDFs? 😩 **Gamma AI Watermark Remover** is designed to help! ✨ This web application specifically targets and eliminates the watermarks added by Gamma AI to their exported PDF presentations when using the free version.  It analyzes your PDF files, detects the characteristic Gamma AI watermark, and removes it, giving you clean, professional-looking documents. Think of it as a specialized cleaner for your Gamma AI PDFs! ✍️

## 🤔 Why do need it?

Gamma AI is a fantastic tool, but the watermarks in the free version can be problematic, especially for educational and professional use cases. 😖

* **Distracting in Presentations & Study Materials:** Gamma AI watermarks can be distracting when presenting information or using PDFs for study. They detract from the content itself. 🙅‍♀️
* **Unprofessional Look:** For presentations intended for a more formal setting (school projects, professional pitches, etc.), watermarks can make the document look less polished and professional. 😠
* **Improving Focus and Clarity:** Clean, watermark-free PDFs are simply easier to read and focus on. Removing the watermark ensures the focus remains on your content. 🙌
* **Using Free Tools Effectively:**  Gamma AI's free tier is great for accessibility. This tool allows you to leverage the free tier and still get clean, watermark-free PDFs when needed, without necessarily needing to pay for a premium subscription just to remove watermarks. 😉

**Gamma AI Watermark Remover** is here to help you:

* **Clean up Gamma AI Presentation PDFs:**  Get rid of the Gamma AI branding and watermarks that are unwanted in your final documents. 🧹
* **Enhance Presentation Readability:** Make your Gamma AI-generated presentations and notes easier and more professional by removing visual distractions, leading to better communication and comprehension. 👀
* **Optimize Presentation Quality:** Create cleaner and more focused presentations, free from unnecessary branding, ensuring your content takes center stage. ✨

## ⚙️ How does it work?

This tool is specifically designed to target Gamma AI watermarks using an intelligent approach: 🧠

1. **PDF Parsing:** It examines your PDF document page by page using the `fitz` (PyMuPDF) library. 🕵️‍♀️
2. **Image Extraction:** It extracts all images embedded within the PDF, as Gamma AI watermarks are typically image-based. 🖼️
3. **Targeted Watermark Detection (Gamma AI Specific):**  Here's the key! ✨ It uses a pre-trained "template" histogram that is characteristic of **Gamma AI's watermarks**. This template is compared to the histograms of each image in your PDF. This allows it to **specifically identify and target images that visually match the Gamma AI watermark style.**  It's like teaching the tool to recognize *exactly* what a Gamma AI watermark looks like! 🤖
4. **Similarity Threshold (Gamma AI Optimized):** The similarity threshold is pre-configured (and can be adjusted in the code) to be highly sensitive to Gamma AI watermark characteristics, ensuring accurate identification and removal. ⚖️
5. **Watermark Removal:** Once a Gamma AI watermark image is identified, the tool carefully removes it from the PDF structure using `fitz`. ✂️
6. **Clean Output:**  You receive a new PDF that is free from the Gamma AI watermark, ready for presentations, studying, or sharing! 🎉

---

## 🚀 Get Started - Installation & Running

Ready to remove those Gamma AI watermarks from your presentations? Here's how to get **Gamma AI Watermark Remover** running:

### 🛠️ Installation (via Cloning)

1. **Clone the Repository:**  Clone this GitHub repository to your local machine:

   ```bash
   git clone https://github.com/DedInc/gamma-ai-watermark-remover.git
   cd gamma-ai-watermark-remover
   ```

2. **Create and Activate a Virtual Environment (Recommended):**

   ```bash
   python3 -m venv venv-gamma
   source venv-gamma/bin/activate
   ```
   *(On Windows, use `venv-gamma\Scripts\activate` instead of the above activate command.)*

3. **Install Python Dependencies:**

   ```bash
   pip install quart PyMuPDF numpy pillow werkzeug
   ```
   *(Using a virtual environment (`venv` or `conda`) is highly recommended to keep your project dependencies isolated. If you're using one, activate it before running `pip install`.)*

   **Dependencies Explained:**
   * `quart`:  A Python web framework (like Flask, but asynchronous!) for the web application.
   * `PyMuPDF (fitz)`:  For PDF processing: reading, image extraction, and modification.
   * `Pillow (PIL)`:  Python Imaging Library for image manipulation and histogram analysis.
   * `Werkzeug`:  Utility library for Python web applications (used by Quart).
   * `numpy`:  For numerical operations, especially histogram calculations for image comparison.

### ▶️ Running the Application

1. **Navigate to the Application Directory:** Open your terminal in the root directory of the cloned repository (where `app.py` is).

2. **Run the Application with Hypercorn (Recommended):**

   ```bash
   hypercorn app:app
   ```

   This will launch the server at `http://127.0.0.1:8000/` by default.

   > **Note:** Using Hypercorn is recommended for running Quart apps, as it provides proper ASGI support and avoids issues with the built-in development server (such as pages loading indefinitely).

3. **(Optional) For Development Only:**

   You can still use the Quart development server for quick tests:
   ```bash
   quart run
   ```
   But for best results, especially with async code, use Hypercorn as shown above.

4. **Open in your Browser:** Access the address displayed in your terminal (usually `http://127.0.0.1:8000/`) in your web browser. You should see the **Gamma AI Watermark Remover** web interface.

5. **Upload and Remove!**  Click "Choose PDF File", select your Gamma AI presentation PDF, and click "Remove Watermark".  The watermark-free PDF will be downloaded.

---

## <div align="center"> ✨ Enjoy your clean, Gamma AI watermark-free PDFs! Happy presenting and studying! ✨ </div>
