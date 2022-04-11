# HsMM-MAR_testing
Repository to test BSD toolbox on real data. The problem until now has been that using the MAR model on real data results in short (1 point-long) state durations.

## DATA
Inside the data folder there is a segment and noSegment folder. The eeg_rest directory inside each of those is the result from lcmv beamforming with the fieldtrip toolbox. Segment and noSegment differ in the method for calculating the covariance matrix for the spatial filter. It is preferable to use the noSegmented data from previous discussions with the group.

The data is too large to upload to a github repository. A link to the source reconstruction data along with the electrode data will be provided.
The output for the models are also too big to be uploaded to github.

## HsMM-MAR pipelines
Previous scripts for analyzing the data with varied settings have been tested. Following the name of the standard scripts for HsMM-MAR analysis with real data that resulted from following the tutorial examples:

Most scripts are arranged in sections:
1. Add directories to matlab's path
2. Load data. In some scripts concatenation of multiple files can happen.
3. Data transformation and preprocessing. Filtering, n° of components and other steps like standarization are included in this.
4. Initialization options
5. Defining the model and passing the structural connectivity matrix.
6. Training the model
7. Saving Output
8. Ploting figures

Scripts:

1. pipeline_hsmm_example_MAR.m - This pipeline uses the concatenated data from multiple subjects. This includes the structural connectivity matrix. Preprocessing: Downsamples to 200 Hz. Filters from 1-30 Hz. Standardize data (z-score) per subject (this actually happens at the concatenation step in the subjcat function). If it takes too much RAM. The number of subjects analyzed (concatenated files) can be changes by specifying a fixed number in the concatenation function. Like so:

  `data_container.eeg_rest = subjcat(files(1:3),1))`

  This will concatenate files 1 to 3 instead of every .mat file in the folder.
