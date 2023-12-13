# About Predict Interpret
Using some simulated data, a machine learning (AI) system has learned to associate the values of several attributes to the outcome "{prediction_title}" for a group of {instance_name}s. The system can learn about inter-related attributes; it does not just consider each one separately. A set of new {instance_name} records were created and some predictions about the outcome made on the basis of the attributes for each one. The prediction is in the form of a probability of "{prediction_title}" and an explanation in the form of an influence diagram.

## How to Interpret the Influence Diagrams
A different influence diagram is shown for each of a number of {instance_name}s. The diagrams should be read from the bottom upwards, following the black arrows.

"Base" shows the average probability of "{prediction_title}" for a {instance_name}, i.e. the best estimate if no attributes are known. Each row shows, for that {instance_name}, the change in "{prediction_title}" which the system assigns on the basis of knowing the attribute value. Bars towards the left, colour-coded blue, mean a reduced probability, while those towards the right, colour-coded pink, mean an increased probability. Hovering the mouse cursor over a bar shows the numerical impact/uplift.

The top grey circle marks the overall probability for the {instance_name} in focus.

## Using "Your Tag"
A box labelled "Your Tag" may be used to put a word of phrase which can be used to find your submissions at a later date and may be shown to other users. This can be anything you choose.

## Notes
If you return to a record and submit a new response, only the latest one will be shown in the Review view.