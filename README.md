# fl2k-examples
This repository contains example flowgraphs for osmo-fl2k. These perform offline computation of samples which then can be transmitted with fl2k_file.

See https://osmocom.org/projects/osmo-fl2k/wiki for more information.

Note: Before transmitting any of those signals, you need to calibrate the clock error of your device first. You then need to adapt the 'ppm' variable in the flowgraphs according to your error.

Depending on the accuracy of your system clock, fl2k_test can be used for a coarse calibration. For fine calibration, the recommended approach is to use the GSM flowgraph, and then synchronize to the transmitted channel with [grgsm_livemon](https://github.com/ptrkrysik/gr-gsm), e.g. with an rtl-sdr. The GSM folder contains a patch for gr-gsm that outputs the clock error. You then can compare the clock error you get from your own transmitted GSM channel to a real GSM base station in order to determine the clock error of the FL2000 dongle.
