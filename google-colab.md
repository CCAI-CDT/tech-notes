<!-- spell-checker:words Colab ipynb -->

# A Guide to Google Colab

## Introduction

[Jupyter Notebooks](https://jupyter.org/) are interactive documents that can contain a mix of narrative text cells, where you can document and explain your work, and code cells, where you can write Python code to perform calculations and run them like:

```python
1 + 1
```
> 2

This combination of rich text, code, results and visualisations makes Jupyter Notebooks a popular tool in scientific and research environments, used both in academia and industry. You will learn more about them and use them in your AI Studio module.

[Google Colab](https://colab.research.google.com/) (short for Co-laboratory) is a cloud-based service that runs Jupyter Notebooks. With Colab you can create, collaborate on and share Notebooks from the web without having to set up anything on your machine.


## Getting Started

To get started with Google Colab, you need a web browser and a Google account.

To create a new Colab Notebook:
1. Log into your Google Account
2. Go to https://colab.research.google.com/
3. Click on "New Notebook"

Notebooks will be saved to your Google Drive by default.

Alternatively, you can make a copy of an existing notebook by clicking the `Copy to Drive` button or clicking `"File" > "Save a copy in Drive"` when viewing it.

You can try to create a copy of this notebook and edit it.

**Note:** Giving your notebook clear, meaningful names is good practice. To edit the name of a notebook, click the file name (default is `Untitled1.ipynb`) on the upper left part of the page.


## Cells

A Colab Notebook is made of cells, mainly **text cells** and **code cells**.


### Text Cells

Text cells can be used to write notes, document the code, provide explanations, etc. They are formatted using Markdown (see below).

To add a text cell, you can do any of the following:
- Click the `+ Text` button from the toolbar
- Click `"Insert">"Text Cell"` the top toolbar
- Hover between cells and click the `+ Text` button

To edit a text cell, you can:
- Double click on it
- Select it and click the Edit button (pencil icon) from the cell's toolbar.



### Code Cells

Code cells are where you write and run your python code. They have an output area to display the results of running the code.

To add a code cell:

- Click the `"+ Code"` button
- Use `"Insert" > "Code cell"`
- Hover between cells and click the `+ Code` button

Once you add the cell, you can write your code, but you won't see the result until you run the cell. To run a code cell:

- Click the `Run Cell` button (▶) that appears when you hover over the cell
- Press Shift + Enter while the cell is selected

Try creating and running a code cell that looks like this:

```python
5 * 11
```

To edit a code cell, you just need to click it. 

Note that **the order in which you run code cells matter**. This will be important later as you start exploring variables, functions and more complex code.


### Selecting, Reordering and Deleting Cells

Click a cell to select it. You will see a grey shadow border around it to indicate that its selected.

Use the toolbar above the selected cell to:
- Move the cell up or down
- Cut/Copy the cell
- Delete the cell


# Markdown
Markdown is a simple formatting syntax used in text cells. In this notebook, we will be covering some of the essentials. For more details check:
- [Markdown Guide - Colab](https://colab.research.google.com/notebooks/markdown_guide.ipynb#scrollTo=5Y3CStVkLxqt)
- [Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/)


## Headings
To insert section headings, like the one above, you use a hashtag symbol `#` before the heading title. The number of hashtags indicates the heading level, with heading level one being the main heading in the page.

Example:
```
# Heading Level 1
## Heading Level 2
### Heading Level 3
```


## Text Styling

To make text **bold**, you surround it with `__` or `**`. Example: `This is a **bold text**`

To _italicise_ text, you surround it with `_` or `*`. Example: `I like _italics_`

To ~~strike-through~~ text, you surround it with `~~`. Example: `I ~~don't~~ know how to format text`


## New Paragraphs

Nobody likes long, unformatted walls of text. Separating paragraphs is important for readability. To separate two paragraphs, add a blank line between them. For example:

```
This is paragraph one.
This is still part of paragraph one.

This is paragraph two. There's a blank space above it to separate it from paragraph one.
```

This renders as:

This is paragraph one.
This is still part of paragraph one.

This is paragraph two. There's a blank space above it to separate it from paragraph one.


## Lists

**Numbered lists**:

```
1. First item
2. Second item
   1. Nested item
   2. Another nested item
3. Third item
```

shows as:

1. First item
2. Second item
   1. Nested item
   2. Another nested item
3. Third item

**Bulleted lists** can be done in a few different ways:

```
- Item one
+ Item two
* Item three
  - Nested item
```

shows as:

- list item
+ list item
* list item

**Task lists**:

```
- [ ] Unchecked item
- [x] Checked item
- [ ] Unchecked item
```
shows as:

- [ ] Unchecked item
- [x] Checked item
- [ ] Unchecked item


## Links

You can add links to your Markdown text to reference external resources or other parts of your notebook. To create a link, you format it as `[Link Text](URL)`. For example:

```
Check out [Google's homepage](https://www.google.com).
```
This will appear as: Check out [Google's homepage](https://www.google.com).


You can also create automatic links for URLs by enclosing them in angle brackets:

`<https://www.python.org>` results in https://www.python.org


## Images

You can embed images in your Markdown cells using a syntax similar to links, but with an exclamation mark at the beginning:
```
![Alt Text](Image URL)
```

For example, `![Dog](https://place.dog/400/300)` will show as:

![Dog](https://place.dog/400/300)


# A Bit of Python

## Introduction

Python is a general-purpose programming language widely used in data science, AI, and machine learning. It also happens to be the language that Google Colab supports.

So far, we've only used code that performs simple calculations, like `5 * 11` or `1 + 1`, but we can do so much more with python, like trying to answer the age old question of: How much pasta do I need to cook?

## Pasta for Two

Let's start with a pasta portion for two. Portion size is selected based on the data from most pasta package instructions sold in the UK. Add a code cell to include then run the following code:

```python
person_count = 2
grams_per_person = 80

total_grams = person_count * grams_per_person

print(f"For {person_count} people, you need {total_grams} grams of pasta.")
```
> For 2 people, you need 160 grams of pasta.

Let's break down what's happening here:

### Variables

In the first three lines, we're using variables. A variable is like a labeled container that holds a value.

`person_count = 2` creates a variable called `person_count` and stores the value 2 in it. Similarly,
`grams_per_person = 80` creates a variable called `grams_per_person` and stores the number `80` in it.
Variables can store different types of values, like numbers, text (strings), lists, and so on.

Variables can also be assigned mathematical operations. `total_grams` is assigned the value of `person_count * grams_per_person`

### Print

print() is a python function used to display output. Whatever you put inside the parentheses will be shown when the code runs.

### F-string

The f"..." is called an f-string. It allows us to embed variables directly in our text, making it easy to create formatted strings.


## Pasta for How Many

Now imagine you want to cook pasta for 3 people. You can rewrite the same code and change the value of `person_count` to 3. This works well, but then what if you wanted to cook for 4, or some other number of people? You can avoid having to re-write the same code over and over again by turning it into a **function**.

Functions are reusable pieces of code. They are a set of instructions that can have inputs and may return outputs.

This is what our new pasta function looks like:

```python
def calculate_pasta(person_count):
    grams_per_person = 80
    total_grams = person_count * grams_per_person
    print(f"For {person_count} people, you need {total_grams} grams of pasta.")
```

Running the code above doesn't show anything in the output panel, but it defines a function called `calculate_pasta` that will print how much pasta we need when it is used. It expect one input, `person_count`. Make sure to run the code above first, then run the code below to count how much pasta you need for 3 people:

```python
number_of_people = 3
calculate_pasta(number_of_people)
```

Try to call the function again for a different number of people.

Feel free to experiment. You can change the function to have your preferred portion size (`grams_per_person`), or have it print a different text, or write a new function that does something completely different. Google Colab is your playground!


# Resources

A few suggested resources:

## Jupyter Notebooks

- This text was **heavily** inspired by [Jupyter Notebook 101](https://www.kaggle.com/code/jhoward/jupyter-notebook-101/notebook)

## Colab

- [Colab intro & guides](https://colab.research.google.com/#scrollTo=-Rh3-Vt9Nev9)
- [Colab useful shortcuts](https://colab.research.google.com/drive/13IO3-gfyS9mSPuzAo6-wsYBUOVpxb_va?usp=sharing#scrollTo=JvHqpL94zh_7)

## Python

- [Python for beginners - Microsoft Training](https://learn.microsoft.com/en-us/training/paths/beginner-python/)
- [The Python Tutorial](https://docs.python.org/3/tutorial/)

