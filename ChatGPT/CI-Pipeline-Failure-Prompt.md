# PROMPT:
----------------------
A developer just committed code to my repository and the CI pipeline failed.  
Here are the details of the failure:

- Pipeline provider: [e.g., GitHub Actions, GitLab CI, Jenkins]
- Error logs: [paste the relevant error messages or stack traces]
- Programming language / framework: [e.g., Python/Django, Node.js/React]
- Recent changes in commit: [brief description or diff]

Can you help me:
1. Identify the likely cause of the CI failure.
2. Suggest steps to fix it.
3. Recommend best practices to prevent similar CI failures in the future.

----------------------------

# 📥 Sample Input

### Pipeline Provider
GitHub Actions

### Programming Language / Framework
- Python
- Django
- Pytest

### Error Logs
```text
Run pytest
==================================== ERRORS ====================================
________________ ERROR collecting tests/test_user_api.py _______________________
ImportError while importing test module '/home/runner/work/app/tests/test_user_api.py'.

Traceback:
app/views.py:3: in <module>
    from rest_framework.decorators import api_view

ModuleNotFoundError: No module named 'rest_framework'

Error: Process completed with exit code 1.
```

### Recent Commit Changes
```diff
commit 2a7f3c9

+ from rest_framework.decorators import api_view
+ from rest_framework.response import Response
```

### CI Workflow File
```yaml
name: CI

on: [push]

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3

      - name: Setup Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.10'

      - name: Install dependencies
        run: pip install -r requirements.txt

      - name: Run tests
        run: pytest
```

----------------------------

# 📤 Sample Output

## 1. Likely Cause of Failure

The CI pipeline failed because the module `rest_framework` is being imported in the code but is not installed in the CI environment.

The error indicates that **Django REST Framework** was added in the code but not added to the `requirements.txt` file.

---

## 2. Steps to Fix the Issue

### Step 1 – Add Missing Dependency

Add the following to `requirements.txt`:

```text
djangorestframework>=3.14
```

### Step 2 – Install and Freeze Dependencies

```bash
pip install djangorestframework
pip freeze > requirements.txt
```

### Step 3 – Commit and Push Changes

```bash
git add requirements.txt
git commit -m "Add Django REST Framework dependency"
git push
```

The CI pipeline will run again and should succeed.

---

## 3. Best Practices to Prevent CI Failures

### Keep Dependencies Updated
Always update dependency files when adding new libraries.

### Test Before Pushing
Run tests locally before committing code.

```bash
pytest
```

### Use Dependency Locking
Use tools like:
- Poetry
- Pipenv

### Run CI in Clean Environments
Use containers (Docker) or reproducible environments in CI.

### Add Dependency Checks
You can add an additional step in CI:

```bash
pip check
```

---

## ✅ Summary

The failure occurred because a new dependency was introduced in the code but not included in the dependency file. Updating `requirements.txt` resolves the issue and allows the CI pipeline to complete successfully.
