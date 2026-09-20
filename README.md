# SQL Injection and XSS Testing Notebooks

This project contains Jupyter notebooks and payload lists for testing SQL injection and reflected XSS behavior in a controlled security testing environment.

The notebooks use Python to send SQL injection and XSS payloads to test URLs, URL parameters, and HTML form inputs. They then analyze the HTTP response content for common signs of vulnerable behavior.

## About the Test URLs

The `sqlinj/url.txt` file contains intentionally vulnerable test links prepared for vulnerability testing. These URLs are safe to keep in the repository and share on GitHub because they are used as demo/lab targets for security testing practice.

Do not replace them with real third-party or production URLs unless you have explicit permission to test those systems.

## Features

- SQL injection testing with predefined payloads
- Reflected XSS testing with predefined payloads
- GET-based URL parameter testing
- POST/form-based testing examples
- HTML form and input discovery with BeautifulSoup
- Simple response analysis using Python and regular expressions
- Educational notebook-based workflow for learning web vulnerability testing

## Project Structure

```text
.
├── README.md
└── sqlinj/
    ├── 19211010.ipynb
    ├── post.ipynb
    ├── Untitled.ipynb
    ├── Untitled1.ipynb
    ├── deneme.ipynb
    ├── payloads.txt
    ├── xss_payloads.txt
    └── url.txt
```

## File Descriptions

| File | Description |
| --- | --- |
| `sqlinj/19211010.ipynb` | Main notebook that combines SQL injection and XSS test examples. It reads payloads and URLs from text files, sends requests, and checks responses for possible vulnerabilities. |
| `sqlinj/post.ipynb` | Focuses on HTML forms and POST-based testing. It discovers form inputs, sends SQLi/XSS payloads, and checks returned responses. |
| `sqlinj/Untitled.ipynb` | Early exploratory notebook for sending requests to a test target, inspecting responses, parsing HTML, and detecting SQL error messages. |
| `sqlinj/Untitled1.ipynb` | URL-list based testing notebook. It loops through URLs and payloads, builds test requests, and includes XSS input/link testing examples. |
| `sqlinj/sql_payloads.txt` | SQL injection payload list used by the notebooks. |
| `sqlinj/xss_payloads.txt` | XSS payload list used by the notebooks. |
| `sqlinj/url.txt` | Safe demo/lab URLs prepared for vulnerability testing. |

## Technologies Used

- Python 3
- Jupyter Notebook
- `requests`
- `beautifulsoup4`
- `lxml`
- `re`

Some experimental cells also use standard Python modules such as `sqlite3` and `tkinter`.

## Installation

Before running the notebooks, make sure Python 3 and Jupyter Notebook are installed on your computer. If you use Anaconda, Jupyter is usually already included.

### 1. Clone the Repository

Download the project from GitHub:

```bash
git clone https://github.com/your-username/Sql-Injection.git
cd Sql-Injection
```

Replace `your-username` with your GitHub username or the owner of the repository.

### 2. Install Dependencies

Install the Python packages required by the notebooks:

```bash
python -m pip install --upgrade pip
pip install notebook requests beautifulsoup4 lxml
```

If you already have Jupyter installed, you can install only the missing packages:

```bash
pip install requests beautifulsoup4 lxml
```

Package purpose:

- `notebook`: opens and runs `.ipynb` files
- `requests`: sends HTTP GET and POST requests
- `beautifulsoup4`: parses HTML pages and forms
- `lxml`: improves HTML/XML parsing support

### 3. Start Jupyter Notebook

Run Jupyter from the project folder:

```bash
jupyter notebook
```

Your browser will open the Jupyter interface. From there, open the `sqlinj/` folder and run the notebooks cell by cell.

Using a virtual environment is optional. It can help keep dependencies isolated, but it is not required for this project if you are opening the notebooks directly in Jupyter or Anaconda.

## Usage

1. Open `sqlinj/19211010.ipynb` for the main SQL injection and XSS testing workflow.
2. Use `sqlinj/post.ipynb` for form-based and POST request testing examples.
3. Keep the payload files in the same folder as the notebooks.
4. Run the notebook cells step by step.
5. Review the printed results and manually verify any possible finding.

## How It Works

For SQL injection tests, the notebooks append payloads from `sql_payloads.txt` to URL parameters or submit them through form inputs. They then search the response body for common SQL error indicators.

For XSS tests, the notebooks send payloads from `xss_payloads.txt` and check whether the payload is reflected in the response content.

This approach is simple and educational. It can produce false positives or false negatives, so results should always be manually reviewed.

## Responsible Use

This project is intended for educational use and authorized security testing only. Use it only on demo targets, lab environments, or systems where you have permission to perform vulnerability testing.

The author is not responsible for misuse, unauthorized testing, service disruption, or legal consequences caused by improper use.
