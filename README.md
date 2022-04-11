# HsMM-MAR_testing
Repository to test BSD toolbox on real data. The problem until now has been that using the MAR model on real data results in short (1 point-long) state durations.

## DATA
Inside the data folder there is a segment and noSegment folder. The eeg_rest directory inside each of those is the result from lcmv beamforming with the fieldtrip toolbox. Segment and noSegment differ in the method for calculating the covariance matrix for the spatial filter. It is preferable to use the noSegmented data from previous discussions with the group.

The data is too large to upload to a github repository. A link to the source reconstruction data along with the electrode data will be provided.
The output for the models are also too big to be uploaded to github.

## HsMM-MAR pipelines
Previous scripts for analyzing the data with varied settings have been tested. Following the name of the standard scripts for HsMM-MAR analysis with real data that resulted from following the tutorial examples:

