# PDF Merger & Splitter (Python)

A simple Python script to **merge multiple PDF files into one** and **split a PDF into individual pages** using `PyPDF2` and `pdfplumber`.

This project is useful for quick PDF manipulation tasks without relying on online tools.

---

## 📌 Features

- ✅ Merge multiple PDF files into a single PDF
- ✅ Split a PDF into individual page-wise PDFs
- ✅ Lightweight and easy to use
- ✅ Command-line friendly

---

## 🛠️ Requirements

Make sure you have **Python 3.7+** installed.

Install the required libraries:

```bash
pip install PyPDF2 pdfplumber
📂 Project Structure
.
├── merge_split_pdf.py
├── Data-driven Decision Making (D3M) - Reading Material.pdf
├── ROLE PLAY.pdf
├── merged_output.pdf
├── page_1.pdf
├── page_2.pdf
└── README.md
🚀 Usage
1️⃣ Import Required Libraries
from PyPDF2 import PdfMerger, PdfReader, PdfWriter
import pdfplumber
import os
2️⃣ Merge Multiple PDFs
def merge_pdfs(pdf_list, output_name):
    merger = PdfMerger()
    
    for pdf in pdf_list:
        merger.append(pdf)
        
    merger.write(output_name)
    merger.close()
    
    print("PDF files merged successfully")
Example:

pdfs = (
    "Data-driven Decision Making (D3M) - Reading Material.pdf",
    "ROLE PLAY.pdf"
)

merge_pdfs(pdfs, "merged_output.pdf")
3️⃣ Split a PDF into Individual Pages
def split_pdf(pdf_file):
    reader = PdfReader(pdf_file)
    total_pages = len(reader.pages)
    
    for i in range(total_pages):
        writer = PdfWriter()
        writer.add_page(reader.pages[i])
        
        output_name = f"page_{i+1}.pdf"
        with open(output_name, "wb") as f:
            writer.write(f)
    
    print("✅ PDF split into individual pages!")
Example:

split_pdf("merged_output.pdf")
📄 Output
merged_output.pdf → Combined PDF file

page_1.pdf, page_2.pdf, ... → Individual pages after splitting

📚 Libraries Used
PyPDF2 – PDF merging and splitting

pdfplumber – Advanced PDF processing support

os – File system operations

🤝 Contributing
Contributions are welcome!
Feel free to fork the repository and submit a pull request.

# Author
Avi Sharma
