THIS REPOSITORY IS LOOKING FOR A MAINTAINER. IF YOU USE THIS TOOL, CONSIDER MAINTAINING IT.

# the fMRIb EEGLAB plugin

This plugin for EEGLAB adds a menu item under 'Tools' called
'FMRIB Tools' for removing artifacts form EEG data collected with FMRI.

Instructions:
	Place the folder fmribX.X (X.X depends on version) inside the 
'plugins' folder of EEGLAB.  When you run EEGLAB the plugin  will be 
detected and installed.  You should see the following message in Matlab 
'eeglab: adding plugin "fmrib1.0b" (see >> help eegplugin_fmrib)'
when you start EEGLAB.

Tools:
1. FASTR (fmri artifact slice template removal):  This tool only 
requires that EEG data in EEGLAB to have timing events for each FMRI slice 
acquisition.  It uses this information to robustly subtract the gradient 
artifact.  More information about the algorithm used is available in the 
plugin documentation.

2. QRS detection.  This tool allows the detection of heart beat /QRS 
complexes (to be subsequently used in removing hear-related artifact) from 
a single channel of ECG data and stores the results as events in the EEGLAB 
event structure.  It has been working quite robustly even with quite bad ECGs.  Again, documentation and references is included in the plugin.

3. Pulse artifact removal.   Uses events from (2) to remove pulse 
artifacts using different methods of constructing an artifact template. 

Copyright (C) 2004 Rami K. Niazy, FMRIB Centre, University of Oxford rami@fmrib.ox.ac.uk

# Introduction
The FMRIB plugin is included in EEGLAB and was developed in 2005 by Rami Niazi. However it is no longer supported.

Removal of FMRI environment artifacts from EEG data using optimal basis sets. Niazy RK, Beckmann CF, Iannetti GD, Brady JM, Smitha SM. Neuroimage. 2005, 28(3):720-737.

See also

Improved quality of auditory event-related potentials recorded simultaneously with 3-T fMRI: removal of the ballistocardiogram artefact. Debener S, Strobel A, Sorger B, Peters J, Kranczioch C, Engel AK, Goebel R. Neuroimage. 2007, 34(2)587-97.

Other than FMRIB, BERGEN is a very nice EEGLAB plugin for fMRI-EEG. This supports a function which helps to reduce an effect of head movement.

Realignment parameter-informed artefact correction for simultaneous EEG–fMRI recordings. Moosmann M, Schönfelder VH, Specht K, Scheeringa R, Nordby H, Hugdahl K. Neuroimage. 2009, 45(4):1144-50. http://sccn.ucsd.edu/wiki/EEGLAB_Plugins http://fmri.uib.no/tools/bergen_plugin.htm

Another recommended application for this purpose is FASST which is a plug-in for SPM but you can still import data to EEGLAB. This works literally fast, and equipped with a constrained ICA for BCG rejection, which is one of the most sophisticated solutions for BCG rejection.

Rejection of pulse related artefact (PRA) from continuous electroencephalographic (EEG) time series recorded during functional magnetic resonance imaging (fMRI) using constraint independent component analysis (cICA). Leclercq Y, Balteau E, Dang-Vu T, Schabus M, Luxen A, Maquet P, Phillips C. Neuroimage. 2009, 44(3):679-91.

http://www.montefiore.ulg.ac.be/~phillips/FASST.html

# Version history

## Changes in V2.0

1) When the last gradient pulse sequence is too near the end of the EEG
recording, FASTR properly generates a warning but then crashes.  2) When a flat
reference channel is in the dataset, FASTR's adaptive noise cancellation option
tries to correct it, resulting in NaNs.  3) Pulse artifact subtraction function
tries to correct flat reference channels resulting in crash.  4) Pulse artifact
subtraction function trying to correct ECG channel despite being told not to do
so.  5) FASTR's adaptive noise cancellation option tries to correct ECG channel
despite being told not to do so.

See https://sccn.ucsd.edu/bugzilla/show_bug.cgi?id=1520

## Changes in V2.1
Fix version display issue in EEGLAB, no other changes.

