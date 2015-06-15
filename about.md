---
layout: page
title: About
permalink: /about/
---

#Between 2009 and 2014#

The Biomechanical ToolKit project started in 2009. The original goal was to propose tools to be independent of the file formats used by motion capture data system. This was achieved by implementing a container close of the structure used by the [C3D] file format. Thus, more than 20 file formats were implemented between 2009 and 2014 using reverse engineering, developer script,  or company's code. Most of the proprietary file formats used by the motion capture leading companies were implemented. Some of them stores electromyography and force platform data.

  - BSF (AMTI)
  - TDF (BTS Bioengineering)
  - MDF, XMOVE (Codamotion)
  - EMG, HPF (Delsys)
  - ANB, ANC, TRB, TRC (Motion Analysis Corp.)
  - DAT (Kistler)

The released tools gave the possibility to explire, modify, and merge acquisition data. There was four ways to use these tools:

  - As a C++ library (BTK::Core) 
  - As a Matlab toolbox
  - As a Python module
  - As a standalone software (Mokka)

Internally, the code was based on the C3D-like container and a pipeline mechanism (_a la_ [VTK], [ITK]) to process the data (e.g. merge files together, extract ground reaction wrenches, detect gait events). The later was defined by a set of filters linked together by their input(s) and output(s). Thus, the modification of one of the filter's parameters triggers a processing update.

However, with this choice to have a C3D-like internal container (historically, this file format was the one with the largest possibilities to store various kind of data: 3D data, analog data, metadata, events), some problems arisen regarding new technologies' possibilities. The most problematic was the obligation to have a sample frequency for the analog data corresponding to an integer ratio of the video sample frequency. Thus the parsing of some file format were limited or impossible. The second major flaw was related to the pipeline mechanism and the non-generic data type requested by some filters (e.g. an acquisition, a collection of events, a collection of force platforms, etc.).

These flaws limited severely the development of a new objective in the project: the computation of joint kinematics and kinetics based on vendor and published biomechanical models (e.g. Plugin Gait, Helen Hayes, ISB recommendations, CAST, etc.).

#Starting from 2015#

To tackle those major limitations, it was decided to rethink completely the concepts behind BTK. For example:

  - Container
    - It would be possible to store biomechanical models (i.e configuration of segments, joints, etc.) as well as trials (i.e. data acquisition and related protocol information);
    - Each time sequence would have their own sample frequency;
    - The _biomechanical_ objects would have the possibility to manage dynamic properties to easily extend their usage in filters;
  - Filter
    - Only one kind of input/output would be used by the filters;
    - It would be possible to process one data set or severals ones transparently;
  - Model
    - It would possible to compute 3D joint kinematics;
    - It would possible to compute 3D joint kinetics (in case forces and moments are available);
    - It would be possible to support models based on anatomical or functional calibration;
    - It would be possible to create a pipeline with all the filters required to supply a clinical gait analysis.

A brand new C++ API was conceived. This new API was of course inspired by the old one, but also by used third party libraries (e.g [Eigen] and [Qt]). The results gave a more compact API than the old one, but more powerful. The same works was also realized on Mokka. To integrate some [users requested features], and to reflect the modifications proposed inside BTK::Core, major improvements were required.

To be continued...

[C3D]: http://www.c3d.org
[VTK]: http://www.vtk.org
[ITK]: http://www.itk.org
[Eigen]: http://eigen.tuxfamily.org/
[Qt]: http://www.qt.io
[users requested features]: http://mokka.uservoice.com/forums/158152-mokka