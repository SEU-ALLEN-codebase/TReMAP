# TReMAP
Source code forked from [Zhi Zhou's work](https://github.com/Vaa3D/vaa3d_tools/tree/master/released_plugins/v3d_plugins).

A Vaa3D neuron tracing plugin that does a 2D tracing and remapping to the 3D image block.

Made a few changes:

1. Specifiy a marker file to start (without soma auto detection)

2. Option to do swc resample. Before: APP2 resamples its result to step 10 and back to 2, now you either resample to 10 or do nothing. Note resampling is just before 3D remapping, so it doesn't necessarily mean the final step length of your swc.

3. Auto bkg_thr:whole image block's mean + 0.5std, used for both region grow thr and APP2. For APP2 it's decreased by 5, but greater or equal than 0(In the past when it was lower than 0, it could cause a bug).
for 0, it means APP2 would do an auto thresholding(which should be mean + 0.5std, depending on your APP2 version).

Help is also updated.

Also, since the trace_raw command is usually not used or shown in the help, no modification has been done.
