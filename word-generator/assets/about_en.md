# About Word Generator
## Using Word Generator
Simply use the buttons, optionally entering or modifying text in the box:  
- "New Word" generates a full new word, ignoring the existing content of the text box.  
- "Start Word" generates the start of a word, with as many characters as in the "learning window" (see below). After this, you can play around with "Get Probabilities" and either typing one of the characters into the text box or using "Add Character".  
- "Get Probabilities" shows the options for the next character to be generated, along with the probabilities for each. This may include a space and the special [end] tag.  
- "Add Character" chooses the next character from the weighted options as seen in "Get Probabilities". Note that if you type something into the text box which has an ending which the generator has not learned then you will get a warning.

## The Algorithm
The algorithm is simple enough for non-specialists to understand and yet can create some believable output.

The Word Generator is first "trained" by analysing a dataset which usually contains betwen 1000 and 5000 words/phrases, one per line. This creates a "model" which is used to generate new output. It works at the level of single characters, including the space character and some punctuation, and uses a "learning window" of the last N characters (N is often 3). The training step takes each line of the input and looks at N characters at the start, making a tally for each of the characters which comes next. It then moves the window forwards 1 character and adds to the tally. This continues to the end of the line, when a pseudo-character [end] is added to the tally. The result of this is a tally of "what comes next" for each unique N-character pattern seen in the training data.

For example, if we used a 2 character learning window, and trained a model using three words, "word", "woad", "orb", "order", and "worth", we would find (amongst others) tallys such as:  
- for "wo", next letter counts are "r" = 2 and "a" = 1;  
- for "or", next letter counts are "d" = 2, "b" = 1, and "t" = 1;  
- for "ad", next letter counts are "[end]" = 1;  
- for "rd", next letter counts are "e" = 1 and "[end]" = 1;  
- ...

When it comes to using the model to generate some output, a starting sequence of N characters is chosen at random from the set of starts found in the training data. Then characters are added one at a time according to the tally which was learned. This is done by making a random choice of character from those in the tally, weighted according to the tally count.

Following on from the previous example, let us say a word start of "Or" was chosen at random. The next letter could be "d", "b", or "t", with probabilities 50%, 25% and 25% respectively. Supposing a "d" was chosen. The window now contains "rd" and the next character will either by an "e" or the end of the word marker, with an equal probability. Notice that, even with only 5 input words, the generative process can create some new words such as "worb", "ord", "worder". Short learning windows produce more creative models, whereas longer windows tend to be closer to replicating the input examples. The latter point can be rebalanced by using more input examples.