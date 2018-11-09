# agglo_cluster_adjustedMNIST
Adjustment to improve agglomerative clustering (binary partition) on MNIST

Work done mostly on pre processing MNIST dataset. The overarching idea was to account for difference in rotation, 
given all numbers are already centered.

We first 'straightened' the numbers by finding eigenvectors and rotating the number for its highest concentration of pixels 
corresponds to x and y axis (x_test_adj). This resulted in worst performance with the agglomerative clustering.

Then we rotated the matrix by 20 degrees each sides and made an average of the three matrices (with the original). 
The idea was to give some margin to help the algorithm deal with the differences in handwriting, or the angle difference 
still left after the first processing part.

The result is a net increase of 3.5% prediction power on MNIST using these simple pre processing. 
