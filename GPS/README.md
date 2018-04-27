This flowgraph is using https://github.com/osqzss/gps-sdr-sim to generate the
samples needed for transmission.

First run gps-sdr-sim to generate GPS baseband samples:

```
gps-sdr-sim -e brdc3540.14n -l 30.286502,120.032669,100
```

Then upsample them with the GNU Radio flowgraph. It's important to set the ppm variable with the value of your dongle, see the main README.md for details.

You need to generate at least 15-20 GB of samples for fl2k_file, as the GPS receiver needs at least a minute before acquiring a fix.

Put your phone really close to the device and play back the samples with:

```
fl2k_file -s 138e6 /tmp/fl2k_gps.bin
```

If you use a monitoring app, you should see satellites appearing and get a fix eventually.

Recommended apps:
https://f-droid.org/en/packages/com.vonglasow.michael.satstat/

https://play.google.com/store/apps/details?id=com.eclipsim.gpsstatus2
