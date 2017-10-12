# AutoMLN

## Overview

The following is an outline for an unsupervised machine-learning algorithm that recognizes and predicts input patterns in real-time. An agent is a system of information processing inspired by the cognitive functions of the mind. Agents have a collection of interacting memory systems akin to the spychological concepts of short-term and long-term memory. Agents learn by observation and adapt based on the frequency of patterns and their relationships. The result is a knowledge-base with the capacity to recognize observations and predict future events.

An association value is a representation of conditional probability which is calculated between the current observation and the rest of the elements in the buffer, i.e. the previous N observations, then stored in the association matrix. Each  elements current place in the buffer determines the strength of the delta applied to its association value, so more recent observation are more strongly associated with the current observations than those further in the buffer. The association matrix enables the prediction of future observations based on current and previous observations. A significantly large association for the current observation to another signify that the other is likely to occur. The association value indicates the strength of the connection as well as the confidence interval related to the prediction. 

Therefore a system may be understood in terms of a Bayesian network, whose adaptations inherently create a foundation for inference, as well as provide a useful data structure, i.e. directed/labeled associations, which can be used to construct higher level objects like sequences (chains of associations) used to represent episodic memory, which in turn combine to form trees (hierarchies of sequences) used for high level reasoning like considering various alternatives in case a planned action fails, or for creating recursive models of observations that span multiple levels of complexity.

## Examples

The sample space was generated by choosing 1000 random values between 1 and 10 corresponding to one of the possible elements. Periodically the selected element is not random but rather chosen from a subset of elements that represent a pattern. When this occurs, two random elements are chosen from the pattern such that they are observed in close proximity to one another and in turn are more strongly associated.

    Pattern: {1, 4, 7}
    
 ![](https://github.com/CarsonScott/AutoMLN/blob/master/img/Graph.png)

The X and Y axes each represent the set of elements, and the Z axis represents the association values. Each peak represents a pair of elements in the pattern. The trough running diagonally through the center are the associations between elements and themselves, equaL to -1 by default. The rest of the graph in blue represent statistically insignificant or random pairings of elements. 
