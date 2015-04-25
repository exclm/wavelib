# wave Class #
```
wave_object wave_init(char* wname); // Initialize wave object

wname - is the name of the wavelet. See below.

```

### Available Wavelets ###

**Haar** : haar

**Daubechies** : db1,db2,.., ,db15

**Biorthogonal** : bior1.1 ,bior1.3 ,bior1.5 ,bior2.2 ,bior2.4 ,bior2.6 ,bior2.8 ,bior3.1 ,bior3.3 ,bior3.5 ,bior3.7 ,bior3.9 ,bior4.4 ,bior5.5 ,bior6.8

**Coiflets** : coif1,coif2,coif3,coif4,coif5

**Symmlets**: sym2,........, sym10 ( Also known as Daubechies' least asymmetric orthogonal wavelets and represented by the alphanumeric la )

### wave Object Parameters ###

```
        char wname; // Wavelet Name
        int filtlength;// Length of filters. They are of identical length and may be zeropadded to the same length when they are not.
        int lpd_len;// Length of Low Pass Decomposition Filter
        int hpd_len;// Length of High Pass Decomposition Filter
        int lpr_len;// Length of Low Pass Reconstruction Filter
        int hpr_len;// Length of High Pass Reconstruction Filter
        double *lpd; //Low Pass Decomposition Filter
        double *hpd; //High Pass Decomposition Filter
        double *lpr; //Low Pass Reconstruction Filter
        double *hpr; //High Pass Reconstruction Filter

```

### Print wave summary ###

```
     wave_summary(wave_object object); 
```

### Free wave object ###

```
     wave_free(wave_object object);

```