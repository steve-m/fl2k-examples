Follow http://wiki.opendigitalradio.org/Main_Page and http://wiki.opendigitalradio.org/ODR-DabMod in order to generate an ETI file and install odr-dabmod.

Then generate the DAB baseband samples with the following command:

```
odr-dabmod yourensemble.eti -l -g1 -r 2048000 -f odr-dabmod.cf32
```

After running the flowgraph to upsample the baseband samples for the fl2k, run the following command to transmit the samples:
```
fl2k_file -s 138e6 /tmp/fl2k_dab.bin
```

This results in a DAB Ensemble broadcasted at channel 6B.
