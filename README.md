# Crossword_Puzzle_Java

## What this project is trying to do

At a high level, the code is about:

- **Reading a crossword grid**
- **Filling words into the grid**
- **Showing the puzzle in a GUI**
- **Trying different ways to solve or generate crossword layouts**

There are **3 different styles** of code in this repo:

1. **Backtracking crossword solver**
2. **GUI crossword board**
3. **Simple random word placement demo**

---

# Repository contents

## Main files

- `Crossword.java`
- `Crossword2.java`
- `Crossword3.java`
- `Current.java`
- `UpdatedCurrent.java`
- `SHARED.JAVA`
- `puzzle.txt`
- `README.md`
- `Introduction_to_OO_Programming_-_Project_2021.pdf`

---

# Simple explanation of each file

## 1) `puzzle.txt`
This is the **crossword puzzle data file**.

It contains:

- a **13×13 grid**
- clue labels like `O`, `X`, `S`, `H`
- an **ACROSS** clue list
- a **DOWN** clue list

### What the symbols mean
From the code and puzzle layout, the grid appears to use:

- `O` = open/white square, where a letter can go
- `X` = blocked/black square
- `S` = special square, likely a clue-start or shaded square
- `H(...)` = highlighted/starting square with a letter or clue marker

So this file is basically the **map of the crossword**.

---

## 2) `README.md`
This file is very short and only says:

- the project is about setting up Crossword Java
- the problem is in the PDF
- the input is in `puzzle.txt`
- the rest are project files

It does not really explain how to run the program.

---

## 3) `SHARED.JAVA`
This file appears to contain an **unfinished or broken version** of a crossword solver.

### What it seems intended to do
It starts a class called `Crossword` and reads `puzzle.txt`.  
It also stores a list of words and probably tries to place them into a crossword grid.

### Important issue
The code shown here looks incomplete and has obvious problems, such as:

- `switch(square)` where `square` is not defined
- `letter` is used but not declared in the visible part
- it only reads `10` lines from the file even though the puzzle is `13×13`
- parts of the solving logic are missing in the snippet

### Layman summary
This file is probably an **early draft** of the crossword solver, but it is not cleanly finished.

---

## 4) `Crossword.java`
This is the **cleanest-looking crossword engine** in the repository.

### What it does
It defines a crossword board using integers:

- `SOLID = -1000` → blocked square
- `BLANK = -2000` → empty square

It also keeps:

- `board` → the crossword grid
- `words` → the list of words to place
- `usedWords` → which words are already placed
- `currentWords` → where each placed letter belongs

### Main idea
This class is designed to:

- take a crossword board
- take a word list
- try to place each word into the board
- track the solution

### Layman explanation
Think of it like a **puzzle manager** that remembers:

- which boxes are open
- which words have already been used
- which letters belong to which word

This is the most “algorithmic” part of the repo.

---

## 5) `Crossword2.java`
This file is a **small random crossword generator**.

### What it asks for
It expects:

- **3 words**
- separated by spaces

Example:
```text
cat dog sun
```

### What it does
It:

1. checks the input is valid
2. creates a **10×10 grid**
3. fills the grid with `*`
4. tries to place the three words randomly
5. fills the remaining empty cells with random letters
6. prints the finished grid

### Limitations
This is not a real crossword solver.  
It does **not** try to make proper clue intersections the way a human-made crossword does.

### Layman explanation
This is like a **toy demo** that hides 3 words in a square and fills the rest with random letters.

---

## 6) `Crossword3.java`
This file is another **GUI-based crossword app**.

### What it contains
It uses Swing components like:

- `JFrame`
- `JPanel`
- `JTextField`
- `JComboBox`
- `JButton`
- `JScrollPane`

### Main class
The visible class is:

- `Note extends JFrame implements ActionListener`

### What it likely does
It creates a crossword interface where users can:

- see a board
- select a puzzle
- interact with cells
- view across/down hints

### Layman explanation
This is the **windowed version** of the crossword idea.  
Instead of printing text in the console, it tries to show the puzzle in a graphical app.

---

## 7) `Current.java`
This looks like another **GUI crossword version**, similar to `UpdatedCurrent.java`.

### What is visible
It includes:

- a `GUI` class
- `JFrame`, `JPanel`, `JTextField`
- arrays like `pRows`, `pCols`, and `pChars`

These arrays seem to describe:

- where letters go on the crossword board
- which characters should appear in those positions

### Layman explanation
This file is likely the **visual crossword board layout**.

---

## 8) `UpdatedCurrent.java`
This appears to be a more updated version of `Current.java`.

### What it does
It defines:

- `CrosswordPuzzle`
- GUI fields
- crossword position arrays
- letter arrays for the puzzle solution

### Layman explanation
This is probably the **main GUI implementation** the author was improving.

---

# How the project works overall

## Main concept
The repo is about **crossword placement and display**.

There are two major approaches:

### A. Solver approach
The solver tries to:

- take a board
- take a list of words
- place the words into the board correctly

This is the role of files like:

- `Crossword.java`
- `SHARED.JAVA`

### B. GUI approach
The GUI tries to:

- show the crossword in a window
- let the user interact with it

This is the role of files like:

- `Current.java`
- `UpdatedCurrent.java`
- `Crossword3.java`

### C. Random generator approach
A simple demo in:

- `Crossword2.java`

---

# Explanation of the crossword puzzle itself

The file `puzzle.txt` provides a **real crossword puzzle layout**.

It includes clue answers such as:

- `MICHAELPHELPS`
- `HARPO`
- `SWAMI`
- `OSMOSIS`
- `IDA`
- `EVANLYSACEK`
- `CARLLEWIS`
- `BRUCEJENNER`
- `SIR`
- `STARDOM`
- `HAITI`
- `OLAND`
- `PEYTONMANNING`

and more.

These are answers to the clue list in the file.

### Example clue meanings
- “2003, for swimming” → `MICHAEL PHELPS`
- “Mute Marx” → `HARPO`
- “Religious teacher” → `SWAMI`

So the project seems to use **real crossword answers** rather than random words.

---

# What a beginner should know about the code style

This repo mixes several programming ideas:

- **Arrays**
- **Grid handling**
- **Recursion/backtracking**
- **File input**
- **Randomization**
- **Java Swing GUI**

If you are new to Java, the hardest concepts here are probably:

1. **2D arrays**  
   Used for the crossword grid.

2. **Recursion**  
   Used when trying to place words one by one.

3. **Swing GUI programming**  
   Used for the crossword window.

4. **Backtracking**  
   This means:
   - try placing a word
   - if it fails later, undo it
   - try another position

---

# Plain-English summary of the code files

| File | Purpose | Difficulty |
|---|---|---|
| `puzzle.txt` | Stores the crossword grid and clues | Easy |
| `README.md` | Very short project note | Easy |
| `Crossword.java` | Crossword solving engine | Hard |
| `SHARED.JAVA` | Broken/unfinished solver draft | Hard |
| `Crossword2.java` | Random 3-word crossword demo | Medium |
| `Crossword3.java` | GUI crossword window | Hard |
| `Current.java` | GUI crossword layout | Hard |
| `UpdatedCurrent.java` | Updated GUI crossword layout | Hard |

---

# Most important takeaway

This repository is **not one single clean application**.  
It looks like a collection of **student project versions** exploring how to make a crossword puzzle in Java.

If I had to describe it in one sentence:

> This repo is a Java crossword project that includes puzzle data, a solver attempt, a random crossword demo, and GUI-based crossword screens.

---

# What is likely unfinished or messy

Based on the code visible:

- some classes are duplicated
- some package names differ
- some files look like earlier drafts
- some code snippets appear incomplete or inconsistent
- there is no clear single entry point for the whole repo
- the README is too minimal to explain setup

---

# If you want to run or understand it better

The next best step would be to:

1. identify the **main class** you want to run
2. check whether the package names match the folder structure
3. decide whether you want:
   - the solver
   - the GUI
   - the random demo
