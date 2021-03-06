# Visual-Echo
Spatialisation of Reservoir computing networks for display and efficiency purposes.

## The objective
During this project, I will try to spatialize the reservoir of an Echo-State Network for display purposes, but also to take into account the layout of the human brain. I will additionally try to get interesting properties from this network.

## What was done:

* :ballot_box_with_check: Implementation of a basic ESN:
The first step was an implementation of an Echo State Network, in this case to predict Mackey-Glass' series.
It led to an ESN object, with some basic functions and methods.

* :ballot_box_with_check: A basic display:
The next part consisted in displaying this network, here simply by making it into a squared image, and showing the evolution of the activation.

* :ballot_box_with_check: Switch to a prediction of the sinus function.
Since it is easier to predict, it will be easier to see whether the network is completely broken or not. If it isn't, we can then switch back to Mackey-Glass.

* :ballot_box_with_check: The spatialized ESN:
This leads to the main part of the project: to give the neurons a position in the plan, before trying to use different properties and see how it learns.

* :ballot_box_with_check: Properly use the spatialization.
The plan is to try to check to what extent the properties of the ESN are kept, and how to adapt if there are differences.
This is currently undergoing.

* :ballot_box_with_check: Change the train function, so that only the connected neurons are updated, to truly spatialize the output.

* :ballot_box_with_check: Use json format to be able to redraw figures.

* :clock1: Do some documentation, build bibliography : see related works.

* :ballot_box_with_check: Update the display function, and check whether it is working properly.
For ex, use of a constant input + short total length, just to see how the signal propagates.

* :ballot_box_with_check: Delay the training:
Allow the information to go through the reservoir before  

* :clock1: Try to use Voronoi Tesselation for display purpose.  

* :soon: Use neurons modelisation.
  Try different probabilities of connection.


## How to use it:
  This program uses an object "Spatial_ESN". To use it effectively, there are several steps required. if you only want to use the plot with a different input series, you can simply:

  * Initialize the "Spatial_ESN" object, given several hyper parameters (see doc of the function for more details): number_neurons, sparsity, number_input, number_output, spectral_radius, leak_rate
  * Import the data you want as an array.
  * Use the function compare_result with your data(see doc for the complete )

Everything is almost done by the simulation method. But if you want to do something more specific, here is how it is done:
  * Initialize the object
  * Use the begin_record method when you want to start recording the internal state.
  * Use the warmup method to initialize the reservoir, or manually with a while and the update method.
  * Train it using the train method (it is very important to use this, else the network can't work unless you do the regression manually)
  * Use the update method for as long as you want.
  * Use the end_record method to plot the internal state and eventually save it as a .mp4 file.

## Important notes:
  This program is designed for a spatial ESN to predict a temporal series. This means that the expected output is always the input (delayed or not), ie of the same dimension. Some changes would be needed to adapt to different output (use of W_back for exemple, but this would mean changing the training too). However, they were not done since it was not a priority at the moment.

  Additionally, it has only been tested on 1 dimensional input/output (sinus and Mackey glass). Please note there may be errors on data of higher dimension (especially because of the way vectors are handled in numpy, and the use of np.newaxis).

## What is left todo:
I should introduce different types of neurons (having different connecting behaviours), and test different properties on the connectivity to see what's efficient.

* :soon: Build various figures once most of the above is implemented. The purpose is to find an effective learning mechanism, using the tools designed above.
