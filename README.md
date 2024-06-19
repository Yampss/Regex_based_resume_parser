# Regex-Based Resume Parser

This repository contains a project for a regex-based resume parser built using the Natural Language Toolkit (NLTK) in Google Colab. The parser extracts relevant information such as names, contact details, education, skills, and work experience from resumes.

## Table of Contents
1. [Introduction](#introduction)
2. [Features](#features)
3. [Installation](#installation)
4. [Usage](#usage)
5. [File Structure](#file-structure)
6. [Contributing](#contributing)
7. [License](#license)

## Introduction
The resume parser uses regular expressions (regex) along with NLTK to process and extract key information from resumes. This tool is designed to streamline the process of extracting structured data from unstructured resume text, which is crucial for applications like automated hiring systems.

## Features
- **Name Extraction**: Identifies and extracts the candidate's name.
- **Contact Information**: Extracts phone numbers and email addresses.
- **Education Details**: Captures information about educational qualifications.
- **Skills Identification**: Extracts a list of skills mentioned in the resume.
- **Work Experience**: Parses details about the candidate's previous work experience.

## Installation
To use this resume parser, you need to have Google Colab access and some basic Python libraries installed.

### Prerequisites
- Google Account (for using Google Colab)
- Basic knowledge of Python

### Libraries Used
- `NLTK`: For natural language processing
- `re`: For regular expressions
- `pandas`: For handling data in tabular format (optional)

### Steps
1. Clone this repository or download the files to your local machine.
2. Upload the project files to your Google Drive.
3. Open Google Colab and mount your Google Drive:
    ```python
    from google.colab import drive
    drive.mount('/content/drive')
    ```
4. Navigate to the project directory:
    ```python
    %cd /content/drive/MyDrive/your_project_directory/
    ```
5. Install necessary libraries:
    ```python
    !pip install nltk
    !pip install pandas
    ```

## Usage
Follow these steps to run the resume parser:

1. **Load the Resume Files**: Place your resume files (in .txt format) in the specified directory.
2. **Run the Parser**: Execute the cells in the provided Google Colab notebook.
3. **Extracted Data**: The parsed information will be displayed and can be saved in a structured format like CSV.

### Sample Code
Here’s a simple example to get you started:

```python
import re
import nltk

nltk.download('punkt')

# Sample resume text
resume_text = """
John Doe
Email: johndoe@example.com
Phone: (555) 555-5555

Education:
- B.Sc in Computer Science, XYZ University, 2020

Skills:
- Python, Java, Machine Learning

Experience:
- Software Developer at ABC Corp, 2021-present
"""

# Regex patterns
email_pattern = re.compile(r'\b[\w.-]+?@\w+?\.\w+?\b')
phone_pattern = re.compile(r'\(?\b[0-9]{3}\)?[-. ]?[0-9]{3}[-. ]?[0-9]{4}\b')

# Extract email
emails = email_pattern.findall(resume_text)
print(f"Emails: {emails}")

# Extract phone numbers
phones = phone_pattern.findall(resume_text)
print(f"Phone Numbers: {phones}")
```


## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

---

Feel free to open an issue or submit a pull request if you have any questions or suggestions.

Happy Parsing!
