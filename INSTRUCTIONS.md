# Exercise 7: Terminal, Testing & Git 🖥️

> **Goal:** Learn to use the terminal, run tests, and use Git — essential tools for every task.
> This is a hands-on, step-by-step exercise. Follow the instructions in order.

---

## Part 1: Terminal Navigation 📁

Open your terminal (Command Prompt, PowerShell, or Bash) and practice these commands:

### 1.1 — Where Am I?
```bash
# Print your current directory:
pwd                # Linux/Mac
cd                 # Windows (just type cd alone)
```

### 1.2 — List Files
```bash
# See what's in the current directory:
ls                 # Linux/Mac
dir                # Windows

# See detailed info:
ls -la             # Linux/Mac
dir /a             # Windows
```

### 1.3 — Navigate Directories
```bash
# Go into a folder:
cd Product-Track
cd Week-0
cd Exercise-1

# Go back up one level:
cd ..

# Go back to home:
cd ~               # Linux/Mac
cd %USERPROFILE%   # Windows
```

### 1.4 — Read Files from Terminal
```bash
# Print file contents:
cat INSTRUCTIONS.md     # Linux/Mac
type INSTRUCTIONS.md    # Windows
```

---

## Part 2: Running Tests 🧪

### 2.1 — Python Tests (pytest)
Navigate to Exercise-1 and run:
```bash
cd Product-Track/Week-0/Exercise-1
python -m pytest test_exercise.py -v
```

**Reading the output:**
```
test_exercise.py::TestVariables::test_create_variables_returns_four_values PASSED  ← ✅ This test passed
test_exercise.py::TestFunctions::test_rectangle_area_basic FAILED                 ← ❌ This test failed
```

**When a test fails, pytest shows you:**
```
FAILED test_exercise.py::TestFunctions::test_rectangle_area_basic
   assert rectangle_area(5, 3) == 15        ← What was expected
   assert None == 15                         ← What your function returned (None!)
```
This means your function returned `None` instead of `15`. Go fix it!

### 2.2 — JavaScript Tests (Node.js)
Navigate to Exercise-2 and run:
```bash
cd Product-Track/Week-0/Exercise-2
node test_exercise.js
```

### 2.3 — Go Tests
Navigate to Exercise-4 and run:
```bash
cd Product-Track/Week-0/Exercise-4
go test -v
go test -race -v    # Also checks for race conditions!
```

### 2.4 — Java Tests
Navigate to Exercise-5 and run:
```bash
cd Product-Track/Week-0/Exercise-5
javac Starter.java
java Starter
```

---

## Part 3: Git Basics 📝

Git tracks changes to your code. Every task in the simulator expects you to use Git.

### 3.1 — First Time Setup (only do this once)
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### 3.2 — Check Status
```bash
# See what files have been changed/added:
git status
```
You'll see output like:
```
modified:   starter.py        ← You changed this file
Untracked files:
  my_new_file.py              ← Git doesn't know about this file yet
```

### 3.3 — Stage and Commit
```bash
# Stage specific files (tell Git you want to save these changes):
git add starter.py

# Or stage all changed files:
git add .

# Commit (save a snapshot with a message):
git commit -m "Fix off-by-one bug in sum_range function"
```

**Good commit messages describe WHAT you fixed, not WHAT you did:**
- ✅ "Fix off-by-one error in sum_range by using inclusive range"
- ❌ "Changed code"
- ❌ "Fixed bug"

### 3.4 — Create a Branch (for PRs)
```bash
# Create and switch to a new branch:
git checkout -b fix/exercise-1-bugs

# Make your changes, then commit...
git add .
git commit -m "Fix priority queue ordering bug"

# Push your branch:
git push origin fix/exercise-1-bugs
```

### 3.5 — View History
```bash
# See recent commits:
git log --oneline -10

# See what changed in the last commit:
git diff HEAD~1
```

---

## Part 4: Practice Challenge! 🏆

Do this to verify you've learned everything:

1. Navigate to `Exercise-6` in your terminal
2. Run the tests: `python -m pytest test_bugfixes.py -v`
3. See how many fail
4. Fix Bug 1 (off-by-one in `sum_range`)
5. Run tests again — see Bug 1 tests pass
6. Create a Git branch: `git checkout -b fix/exercise-6-bugs`
7. Stage and commit: `git add . && git commit -m "Fix off-by-one in sum_range"`
8. Fix the remaining bugs one by one, committing after each fix
9. Run `git log --oneline` to see your commit history

**If you can do all of the above, you're ready for Week 1! 🎉**
