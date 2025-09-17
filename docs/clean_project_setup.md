##Starting a New Project

# Step 1: Create a new project
poetry new my_project   # creates folder, pyproject.toml, basic structure

# Step 2: Enter project folder
cd my_project

# Step 3: Install dependencies (if any specified later)
poetry install          # sets up virtualenv + installs dependencies

# Step 4: Activate the shell to work inside venv
poetry shell            # opens virtual environment shell


##Activating an Existing Project

# Step 1: Navigate to the project folder
cd my_existing_project

# Step 2: Install dependencies from pyproject.toml (and poetry.lock if exists)
poetry install          # ensures correct versions are installed

# Step 3: Activate virtual environment
poetry shell


##Adding Dependencies

###To a New or Existing Project

# Add a runtime dependency
poetry add requests

# Add a specific version
poetry add requests@^2.31

# Add a dev-only dependency (not needed in production)
poetry add pytest --group dev


##Removing Dependencies

# Remove a dependency
poetry remove requests

# Remove a dev-only dependency
poetry remove pytest


##Cloning an Existing Project (with Dependencies Setup)

# Step 1: Clone the repo
git clone https://github.com/user/repo.git
cd repo

# Step 2: Install dependencies
poetry install   # uses pyproject.toml + poetry.lock

# Step 3: Enter venv
poetry shell



##Using Poetry in New Instances (Docker, New Computer, etc.)

# Step 1: Make sure Poetry is installed on the system
pip install poetry

# Step 2: Copy or clone project into the new environment
git clone <repo> && cd <repo>

# Step 3: Install exact locked versions (recommended for reproducibility)
poetry install --no-root   # install dependencies only, skip building project

# Step 4: Begin work
poetry shell


✅ Key Notes
	•	pyproject.toml → main config (declares dependencies).
	•	poetry.lock → exact dependency versions (for reproducibility).
	•	poetry add/remove updates both files.
	•	Always run poetry install after pulling new changes.