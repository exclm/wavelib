# Wavelet Transform Class ( wt ) and Functions #

### wt Initialization ###
```
wt_object wt_init(wave,method,N,J);


// wave - Wavelet object created using wave_object
// method - Takes char values - "dwt", "swt" and "modwt"
// N - Length of Signal/Time Series
// J - Decomposition Levels

```

### Wavelet Transform Execution ###

```
dwt(wt, inp);// Discrete Wavelet Transform (Decimated)

swt(wt, inp);// Stationary Wavelet Transform (Undecimated)

modwt(wt, inp); // Maximal Overlap Discrete Wavelet Transform (Undecimated)


// obj - wt object
// inp - Input Signal / Time series of length N

```

### Inverse Wavelet Transform Execution ###

```
idwt(wt, dwtop);// Inverse Discrete Wavelet Transform (Decimated)

iswt(wt, dwtop);// Inverse Stationary Wavelet Transform (Undecimated)

imodwt(wt, dwtop); // Inverse Maximal Overlap Discrete Wavelet Transform (Undecimated)


// obj - wt object
// dwtop - Output of length N

```


### wt Object Parameters ###

```
        wave_object wave; // wavelet object
        char method; // "dwt", "swt" or "modwt"
        int siglength;// Length of the original signal.
        int outlength;// Length of the output DWT vector
        int lenlength;// Length of the Output Dimension Vector "length"
        int J; // Number of decomposition Levels
        int MaxIter;// Maximum Iterations J <= MaxIter
        char ext[10];// Type of Extension used - "per" or "sym". Only available for method "dwt". Undecimated transforms use periodic extension only.
        char cmethod[10]; // Convolution Method - "direct" or "FFT". Default is "direct". "FFT" not available for method "modwt"

        int length[102];// Length Vector
        double *output; // DWT Output Vector

```

**Accessing DWT output** 1D vector wt->output stores Output of Discrete Wavelet Transform. It stores coefficients in following format:
```
[A(J) D(J) D(J-1) ..... D(1)]
```

where A(J) is the approximation coefficient vector at the Jth level while D(n) are the detail coefficient vectors at the nth level. wt->length contains the lengths of corresponding vectors. Last entry of the length vector is the length of the original signal.

### wt Functions ###

```
    setDWTExtension(wt_object wt, char *extension);// works only for dwt. Options "per" and "sym"

    setWTConv(wt_object wt, char *cmethod);// Options "direct" and "fft". Not implemented for modwt

    wt_summary(wt_object wt);// Print summary

    wt_free(wt_object object);// Frees wt object

```