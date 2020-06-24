<p align='center'>
  <b>Watch the intro and explanation for this project!</b>
  <a href='https://www.youtube.com/watch?v=5dxZgZjwTaM'><img src='https://user-images.githubusercontent.com/872296/32171715-e02186ce-bd57-11e7-9742-56069329f5a6.png' width=600 /></a><br><sub><a href='https://www.youtube.com/watch?v=5dxZgZjwTaM'>(YouTube Link)</a></sub>
  <hr>
</p>

<!-- Do we want to record a new video for this? -->

# Hangman Game

In this project we're aiming to re-create the game 'Hangman' in Python!

The task broken down into several small functions that, when combined and
completed, form a working game!

We're providing the main function `start_new_game`, that relies on the functions you will write in order to work.

These are the functions that you have to implement:

### Mask Word

```bash
$ py.test tests.py -k mask_word
```

Given a word like `'Python'`, this function will return a "masked" version of the word (replacing real characters with asterisks): `'******'`


### Uncover Word

```bash
$ py.test tests.py -k uncover_word
```

This is probably one of the most challenging ones (it has many exceptional cases). Given the initial conditions of an answer word (like `'Python'`), a masked word (like `'******'` or `'*y****'`), and a guessed letter (`'n'` for example), the function should return a new masked word replacing the asterisks with the guessed letter in the correct position **IF** the letter is present in the answer word. For example:

```python
_uncover_word('Python', '******', 'y')  # '*y****'  # Match
_uncover_word('Python', '*y****', 'n')  # '*y***n'  # Match

_uncover_word('Python', '******', 'x')  # '******'  # Miss
_uncover_word('Python', '*y****', 'x')  # '*y****'  # Miss
```

### Get Random Word

```bash
$ py.test tests.py -k get_random_word
```

This function will receive a list of words and returns one from the list randomly.


### Guess Letter

```bash
$ py.test tests.py -k guess
```

Probably the most "important" (or "general") function. We recommend that you deal with this function **after** you've completed the other ones.

It receives a `game` object and a letter to guess. It has several different scenarios. For example, the guessed word is a match or a miss, the game is won or lost, or the game was already over.
