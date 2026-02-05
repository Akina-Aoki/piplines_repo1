# piplines_repo1
Database Development Course: First repository for pipelines ETL/ELT

# Repo set up
- Git clone / gitinit this repo 

## Installation of FastAPI (lecture version)
- [Installation Documentation](https://fastapi.tiangolo.com/)
- [Installation Guide](https://github.com/Akina-Aoki/FastAPI-Learning-Roadmap/blob/main/02-fastapi-setup-and-installation/2.02-installation.md)
- ALWAYS RUN THE FASTAPI IN THE ROOT FOLDER, NOT SUBFOLDERS

### 1. Create and activate a venv
- From repo root: 
```
python -m venv venv
source venv/Scripts/activate   # Windows (Git Bash)
```
- Activation is verified when (venv) appears in the terminal prompt.

- Confirmation venv is active and works properly:
- ´which python´
- `python -V`
- `pip list`
- `which pip`
### 2. Install FastAPI
- In the terminal `pip install "fastapi[standard]"`
- Successful: `Successfully installed MarkupSafe-3.0.3`

- Environment state should be:
    - (venv) is active
    - venv/ structure is correct (Scripts/, Lib/, etc.)
    - FastAPI is installed
    - Pip is upgraded 

- To confirm of fastapi is installed properly:
`python -c "import fastapi; print(fastapi.__version__)"`
`which uvicorn`

### 2.1 (Optional) Install Jupyter
- MAKE SURE VENV IS ACTIVE FIRST
- `pip install notebook jupyterlab ipywidgets`
- for validation: `jupyter --version`
- OPTIONAL: To launch jupyer lab `python -m jupyter lab`

### 3. FastAPI and PosgreSQL Installation
#### Psycopg
- `pip install "psycopg[binary]"`
- `pip install psycopg[pool]`
- Expecred Output: 
- `Successfully installed psycopg-3.3.2 tzdata-2025.3`
- `Successfully installed psycopg-pool-3.3.0`


- Run: `fastapi dev main.py`
#### PostgreSQL
- (Setup PostgreSQL)[https://www.postgresql.org/download/]

