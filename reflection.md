# Reflection — Lab 5: Static Code Analysis

## 1. Which issues were the easiest to fix, and which were the hardest? Why?
- **Easiest:** Fixing the mutable default argument and adding docstrings. These required only simple syntax changes.
- **Hardest:** Handling file I/O safely and validating inputs because they needed logic changes and exception handling.

## 2. Did the static analysis tools report any false positives? If so, describe one example.
- Most warnings were valid. One possible false positive was a “function unused” message for helper or demo code that’s only called inside `__main__`, which is expected behavior.

## 3. How would you integrate static analysis tools into your actual software development workflow?
- By using `pylint`, `bandit`, and `flake8` in a **pre-commit hook** or CI pipeline so that code with high-severity issues cannot be merged.
- By running linters automatically on every push and fix or justify any remaining warnings before merging.

## 4. What tangible improvements did you observe in the code quality, readability, or robustness after applying the fixes?
- The code is now cleaner, more secure, and easier to maintain.
- Replacing `eval` removed a serious security risk.
- Input validation prevents runtime errors.
- Logging provides clear runtime diagnostics instead of silent failures.
