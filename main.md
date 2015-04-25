# C Implementation of Discrete Wavelet Transform #

An ANSI C implementation of decimated and undecimated 1D Fast Discrete Wavelet Transforms.

**Git Repository**
```
git clone https://code.google.com/p/wavelib/
```
Or Download Zip File From Here
```
https://code.google.com/p/wavelib/source/browse/
```

**Methods Implemented**

**DWT/IDWT** A decimated Discrete Wavelet Transform implementation using implicit signal extension and up/downsampling so it is a fast implementation. A FFT based implementation is optional but will not be usually needed. Both periodic and symmetric options are available.

**SWT/ISWT** Stationary Wavelet Transform. It works only for signal lengths that are multiples of 2^J where J is the number of decomposition levels. For signals of other lengths see MODWT implementation.

**MODWT/IMODWT** Maximal Overlap Discrete Wavelet Transform is another undecimated transform. It is implemented for signals of any length but only orthogonal wavelets (Daubechies, Symlets and Coiflets) can be deployed. This implementation is based on the method laid out in "Wavelet Methods For Wavelet Analysis" by Donald Percival and Andrew Walden.


|**[Usage](https://code.google.com/p/wavelib/wiki/Usage)**| How to integrate wavelib in your code|
|:--------------------------------------------------------|:-------------------------------------|
|**[wave object](https://code.google.com/p/wavelib/wiki/wave)**| Wavelet Object, Parameters and Functions|
|**[wt object](https://code.google.com/p/wavelib/wiki/wt)**| Wavelet Transform Object, Parameters and Functions|
|**[DWT Example Code](https://code.google.com/p/wavelib/wiki/dwtex)**| 1D DWT/IDWT Demo Code|
|**[SWT Example Code](https://code.google.com/p/wavelib/wiki/swtex)**| 1D SWT/ISWT Demo Code|
|**[MODWT Example Code](https://code.google.com/p/wavelib/wiki/modwtex)**| 1D MODWT/IMODWT Demo Code|
