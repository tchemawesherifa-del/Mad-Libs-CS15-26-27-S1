# Activity 1: Mad Libs

In this activity, we will walk through how to create a mad libs style program that uses formatted strings, user input, and variables.

Once you have completed the tutorial portion of this activity, be sure to also complete the [Extension Activity](#extension-activity-create-your-own-mad-lib)

If you'd like you can follow along in [this video here](https://youtu.be/bzqTR1dTEBE?si=v_DO_Q69JvBrJSD9) as well!

## 1. Create a Root Folder

Whenever you are creating a new Python project, it is best to stay organized by placing all the files related to the project in the same folder. Create a folder for this activity.

Inside the folder, create a new `main.py` file.

## 2. Planning out the Mad Lib

Before jumping into programming, we need to plan what the story will be so that we know what kinds of inputs we need. For our example, we will use the following story:

```txt
Today in computer science class, Mr. Forsyth taught us how to program a(n) [NOUN]. First, we clicked the [ADJECTIVE] button, then the computer started [VERB-ING]. Suddenly, [STUDENT NAME] accidentally created [NUMBER] [PLURAL NOUNS]! Mr. Forsyth said, "This is the most [ADJECTIVE] bug I've ever seen."
```

Our inputs will be:

* Noun
* Adjective
* Verb ending in -ing
* Student name
* Number
* Plural noun
* Adjective

## 3. Requesting User Input

Let's start our program off by adding the user inputs. Be sure to provide meaningful prompts.

**Tip:** If you want to clean up your inputs so that the user writes on the next line instead of at the end of your input you can use a new line character (`\n`).

```python main.py
noun = input("Noun\n")
adjective = input("Adjective\n")
verb = input("Verb ending in -ing\n")
name = input("Student name\n")
number = input("Number\n")
plural_noun = input("Plural noun\n")
adjective_2 = input("Another adjective\n")
```

Before we get too far ahead of ourselves, we should test to make sure all of our inputs are being stored correctly. Add a `print()` statement for each one to ensure the values are being stored:

```python main.py
print(noun)

# Add the rest down here on your own!
```

## 4. Formatting the Story with Formatted Strings

Now that we have confirmed all of our values are being stored correctly, it's time to add them to our story! But how? Our story has all of these variables sprinkled throughout!

| Formatted String                                                                        |
|:----------------------------------------------------------------------------------------|
| *A string that allows variables and expressions to be inserted directly into the text.* |

This is where formatted strings come in. Formatted strings (sometimes called "f strings") allow any type of variable (even numbers and booleans) to be placed inside a string and formatted correctly.

To create a formatted string put the letter "f" on the outside of the quotes:

```python
number  = 3
my_string = f""
```

Then to place a variable inside, you just need to wrap it in curly brackets `{}`.

```python
number = 3
my_string = f"My number is: {number}."
print(my_string)
```

```terminaloutput
My number is: 3.
```

To use this in our code, we can create a formatted string that uses *all* of our values:

```python main.py
message = f"Today in computer science class, Mr. Forsyth taught us how to program a(n) {noun}. First, we clicked the {adjective} button, then the computer started {verb}. Suddenly, {name} accidentally created {number} {plural_noun}! Mr. Forsyth said, "This is the most {adjective_2} bug I've ever seen.""
```

One thing you might notice in the code above is that it looks like not all of our text is properly in the string. That's because we used double-quotes (") for our string, but also Mr. Forsyth's dialogue! This means that our string closed early! There are two ways to fix this:

### Fix 1: Using Single Quotes

In programming, we can use single-quotes (') instead of double-quotes. Functionally they are identical, except single-quotes only close other single-quotes, and double-quotes only close other double-quotes. Our new code would look like this:

```python main.py
message = f'Today in computer science class, Mr. Forsyth taught us how to program a(n) {noun}. First, we clicked the {adjective} button, then the computer started {verb}. Suddenly, {name} accidentally created {number} {plural_noun}! Mr. Forsyth said, "This is the most {adjective_2} bug I've ever seen."'
```

But wait, it's still broken! The dialogue has an apostrophe, which still counts as a single-quote and breaks this code!

### Fix 2: Escape Characters

When both kinds of quotes are used, or when you don't want to use both kinds of quotes, we can use an "escape character". An escape character is a special symbol that tells a program "this character doesn't mean what it normally does, it's just meant to be rendered". 

In Python our escape character is `\` and goes before a character that might cause problems. Our fixed code might actually look like this then:

```python main.py
message = f"Today in computer science class, Mr. Forsyth taught us how to program a(n) {noun}. First, we clicked the {adjective} button, then the computer started {verb}. Suddenly, {name} accidentally created {number} {plural_noun}! Mr. Forsyth said, \"This is the most {adjective_2} bug I've ever seen.\""
```

## 5. Output the Story

With everything fixed, it's time to output our mad libs and test it!

Add a print statement to print the message out:

```python main.py
print(message)
```

# Extension Activity: Create Your Own Mad Lib

Create a second Mad Lib program using the same programming concepts from the walkthrough, but with your own original story.

## Requirements

* Ask the user for at least **5 different inputs** and store each response in a variable.
* Create an original story that uses **all of the user's inputs**.
* Use an **f-string** to insert the variables into the story.
* Include **quoted dialogue** and use an **escape character** correctly within the story.
* Display the completed story using `print()`.

