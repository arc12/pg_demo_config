# About Precision, Recall, and Accuracy
We are here concerned with "informed guesses" of a yes/no - i.e. binary - type and whether they are true or false. Although the emphasis is on machine learning or AI, the same concepts apply to people making informed guesses, for example in a game where playing cards are dealt out into a grid, then turned face-down, and the player has to recall where a given suit may be found. We can consider the following to be situations of this type: predicting a future event (e.g. whether a student will pass an exam), a test of condition (e.g. whether an engine will fail on the next journey, whether a medical test will detect disease, or whether a credit card transaction is fraudulent), a classification (e.g. identifying a particular kind of plant from a photograph), a recommendation (e.g. of a learning resource, film, etc), discovery (e.g. locating relevant documents in a search), and such-like.

A simple and common way of measuring how good the informed guesses are is to consider accuracy, but this is often misleading or unsatisfactory for a variety of reasons. Two additional measures of performance are precision and recall (although the same measures also go by other names). Consider a set of items (or events etc) from which our informed guesser selects some as "yes", while the remainder are "no":  
- __Accuracy__ is the fraction or precentage of items where the guess was correct.  
- __Precision__ is the fraction or percentage of items where the guess was "yes" and was correct.  
- __Recall__ is the fraction or percentage of items where the guess was "yes" out of all the items which are really "yes" cases.

These are often expressed in terms of the four different combinations of the guess and whether it was true or false, but rather than "yes" or "no", the terminology is "positive" or "negative". In these terms:  
- __Accuracy__ is the fraction of all items which are either true positives or true negatives.  
- __Precision__ considers the items which are either true positives or false positives, being the fraction which are true positives.  
- __Recall__ considers the items which are either true positives or false negatives (those the guesser missed), being the fraction which are true positives.  

Precision and recall may be particularly useful when we put different value on, for example, a false positive vs a false negative. For example, consider a medical test for a fatal disease. In such cases, an institutional policy might set either a minimum standard or a target for recall. On the other hand, in a resource-constrained setting with lower stakes, there might be a requirement for higher precision. This might be particularly important where the cost of intervention is high; a true positive is worthwhile but a false positive is a costly waste.

For the same informed guesser, higher precision entails lower recall, and _vice versa_; there is a trade-off. If numerical values can be given to each of the yes/no and true/false combinations, an optimal position for the trade-off can be computed.

Another situation where accuracy can become a very poor measure of performance is where the balance between actual "yes" and "no" cases is far from equal. Relatively rare events/items are often the ones we care about (machines breaking, students failing exams, people having fatal disesases, etc). In such cases, always guessing "no" can give a higher accuracy than a useful guesser which focusses on high recall.

Another consideration is that the value of accuracy (and precision and recall) usually depends on how many "yes" guesses are made, so long as the first guesses made are those which the guesser is most confident of (this is how machine learning or AI is usually deployed, as it is for people). There is no single value of accuracy (etc), rather a value which depends on the position of the trade-off.

The bottom line is that the performance of binary informed guesses cannot be captured by a single value of accuracy and must somehow embody values which come from its context of use. A good machine learning or AI system will have been designed to serve its users by its makers discovering their values.