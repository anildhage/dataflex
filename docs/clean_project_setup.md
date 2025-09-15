# Clean Project Setup Guide (macOS + Poetry + pyenv)

This guide explains the **best practices** to set up and work on new Python projects cleanly, end-to-end, using **Poetry** for dependency management and **pyenv** for Python version management.

---

## 1. One-time Setup (Environment)

### Install pyenv
```bash
brew install pyenv      -- already installed
brew update && brew upgrade pyenv   -- do this often
```

### Install Python versions
```bash
pyenv install 3.12.4
pyenv install 3.11.9
pyenv install 3.13.6
brew update && brew upgrade pyenv    -- do this often
```
(Choose versions you need. Newer versions can be installed later.)

### to set your global version
pyenv global 3.13.6

### Install Poetry 
**Homebrew**
```bash
brew install poetry     -- already installed
```
(No extra PATH needed.)

---

## 2. Starting a New Project

1. Create a new project folder:
```bash
poetry new myproject
cd myproject
```


2. Install dependencies:
```bash
poetry install
```
OR

3. Does not create folders or files; it only creates (or updates) pyproject.toml in the current directory.
	•	Prompts you interactively to add dependencies.
	•	Use this when you:
	•	Already have a folder/project (maybe existing code)
	•	Just want to turn it into a Poetry-managed project

---

## 3. Daily Workflow (How to Work on Projects)

### Enter project
```bash
cd myproject
poetry run python manage.py runserver      # start Django server
poetry run pip list                        # see installed packages
poetry run django-admin startapp myapp     # create a new Django app
```
- Activates the project’s virtual environment  
- From here, run Python, install packages, etc.  

### Add dependencies
```bash
poetry add requests
```
(or `poetry add --dev pytest` for dev tools)

### Run scripts inside the env
```bash
python main.py
pytest
```

### Exit when done
```bash
exit
```

---

## 4. Restarting Work (Next Day or After Reboot)

1. Open Terminal  
2. Go to your project:
```bash
cd myproject
```
3. Enter Poetry shell:
```bash
poetry shell
```
Now you’re back in the exact same environment.  

OR
Just do from the folder of the project
```bash
poetry run
```



---

## 5. Best Practices

- **One Python per project**: Keep dependencies isolated.  
- **Lock dependencies**: Always commit `poetry.lock` file.  
- **Don’t mix installers**: Use either Poetry installer or Homebrew, not both.  
- **Version control**: Initialize git early (`git init`).  
- **Clean exit**: Always `exit` your Poetry shell when done.  

---

✅ Following this ensures a **clean, repeatable, conflict-free** setup for every project.
