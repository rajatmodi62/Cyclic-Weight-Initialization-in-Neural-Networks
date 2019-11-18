# Cyclic-Weight-Initialization-in-Neural-Networks

* Background
FastAI lecture 1 [Pets Classification] had shown that there is a decrease in the
classification performance of Resnet18/34 when the entire network is trained without freezing.
An alternate way has been to tune the last layer only.

* Our Approach

We propose the following changes to the Gradient Descent update equation:
