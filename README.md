# RobustApp 1.0 Documentation Site

This project uses [MkDocs](https://www.mkdocs.org/) with the [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) theme to build a beautiful, static documentation site.

## Getting Started

Follow these steps to get the documentation running locally.

### 1. Clone the Repo

```bash
git clone https://github.com/alleFarell/robustapp-doc.git
cd robustapp-doc
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Then activate it:

- **macOS/Linux**:
  ```bash
  source venv/bin/activate
  ```
- **Windows**:
  ```bash
  venv\Scripts\activate
  ```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Docs Locally

```bash
mkdocs serve
```

Then open [http://localhost:8000](http://localhost:8000) in your browser.

## Project Structure

```
.
├── docs/              # Markdown source files
├── mkdocs.yml         # MkDocs configuration file
├── requirements.txt   # Python dependencies
├── .gitignore         # Git ignore file
├── venv/              # Virtual environment (not tracked in Git)
└── README.md          # This file
```

## Useful Commands

- **Start local dev server**:

  ```bash
  mkdocs serve
  ```

- **Build static site (for deployment)**:

  ```bash
  mkdocs build
  ```

- **Deploy to GitHub Pages** (optional):

  ```bash
  mkdocs gh-deploy
  ```

- **GitHub Token Authentication for Deployment** (optional):
  ```bash
  git remote set-url origin https://<token>@github.com/<username>/<repository>
  ```

## Troubleshooting

- Make sure you're using **Python 3.7+**
- If `mkdocs` command isn't found, ensure your virtual environment is activated
- If you clone and run into issues, try deleting the `venv/` and reinstalling with the steps above

## License

This project is open-sourced under the MIT License. See the LICENSE file for more details.
