# 🧾 Automated Lab Report Generator (Python + ReportLab)

This project automatically compiles, runs, and generates PDF lab reports for C++ programming labs.
It takes care of everything — from compiling `.cpp` files and running them with specific test inputs to formatting the results neatly into a professional, university-style PDF with your name, roll number, and department.

# 📸 Sample Output

The generated PDF includes:
- University logo and title page
- Each lab question’s source code
- Automatically captured program output (styled like a terminal)
- Inputs used for testing
- Automatic date and metadata

The PDF can be accessed [here](https://github.com/muhammadrafayasif/labs-to-pdf/blob/main/Lab%201/CT-24000.pdf)

# ⚙️ Features

- Automatic Compilation — Compiles all .cpp files in each lab folder using g++
- Input Injection — Feeds predefined test input to each program
- Output Capture — Captures console output automatically
- Beautiful PDF Generation — Uses ReportLab for clean, formatted lab reports
- Customizable Branding — Add your own logo, name, roll number, department, and degree
- Supports Multiple Labs — Process multiple folders like "Lab 1", "Lab 2", etc. in one go

# 🗂️ Project Structure

```bash
📦 labs-to-pdf/
│
├── Lab 1/
│   ├── q1.cpp
│   ├── q2.cpp
│   └── ...
│
├── logo.png                # University logo for the title page
├── make_pdfs.py
└── README.md
```

# 🧰 Requirements

You’ll need:

- Python 3.8+
- g++ compiler (available in PATH)
- ReportLab for PDF generation

Install dependencies with:
```bash
pip install reportlab
```

# 🧑‍💻 Usage

- Place your .cpp files inside folders like Lab 1, Lab 2, etc.

- Update configuration at the top of the script:
```py
EXTENSION = "cpp"
LOGO_PATH = "./logo.png" # University Logo to be added to the title page
PROCESS = ["Lab 1"] # Add folder names (LABS) to be processed
COMPILE_TEMPLATE = ["g++", "{0}", "-o", "{1}"] # Compilation code to run task

# FORMAT = [ [FIRST LAB INPUTS], [SECOND LAB INPUTS], ... ]
INPUTS = [ 
    ["2 2\n1 3 2 4\n", "2 3\n3.2 3.7 4\n2.3 4 3.2\n", "1\n5\n1\n2\n1\n5\n2\n3\n", "5\n2 13 16 23 35\n16\n", "2 2\n2 5 10 15\n5\n"] 
] # User input for each lab task

UNIVERSITY="NED University of Engineering and Technology"
NAME = "NAME"
ROLL_NO = "CT-24000"
DEPARTMENT = "Department of Computer Science and Information Technology"
DEGREE = "Bachelor of Science (BS)"
```
- Run the generator
```bash
python labs_to_pdf.py
```
- The PDFs will be generated inside each Lab folder individually

# 🧠 Tips

- Make sure your .cpp files compile cleanly without manual input prompts (use the provided test input).
- If a file doesn’t require input, simply set its entry in INPUTS to an empty string "".
- You can customize colors, fonts, and styles by modifying the paragraph and table styles in the script.

# 🪪 License

This project is released under the [MIT License](LICENSE)

Feel free to modify and adapt it for your institution or personal use.
