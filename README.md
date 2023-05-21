# fit-test-hacks
Quick scripts for use with PortaCount 8020A

# Supported platforms

This has only been tested on Linux. Since I'm copy-pasting from a terminal running GNU screen, I'm getting a 0x0A not a 0x0D 0x0A sequence and it's built to parse that. That should be easy to fix if it becomes a problem on other platforms.

# How to connect to the PortaCount 8020A serial terminal

Note on page 4 of the technical addendum[1], in bullet point 5, the DIP switch information about the baud rate settings. Most likely your PortaCount is still set to the factory setting of 1200 baud. You don't need to change that.

The GNU Screen program is very easy to use to connect to the PortaCount using the TSI data cable and a USB to Serial converter. Generally the device will appear on your computer as `/dev/ttyUSB0` when you plug in the converter, but the number may end up being different for you.

This command will create a bidirectional serial connection to the PortaCount. If you run the fit test using controls on the device, or run it in count mode, each fit test you run will be printed out. 

    screen /dev/ttyUSB0 1200

# fitconvert

This script converts the ASCII output of a fit test with a standard 12 exercise sequence, inputted either on stdin or as a file (first argument of the script) and pulls out the 12 fit factors for each exercise. It doesn't output the ambient and mask values, the overall fit factor, pass/fail status, or target fit factor for passing. It outputs as a tab-delimited single line of just the individual exercise fit factors. This is useful for if you're using a spreadsheet for tracking fit exercises and can compute overall fit factor and make your own decisions about what constitutes a pass. 

The output to be parsed here is described in the technical addendum[1] page 7, under "Output in Fit Test Mode".

# References

1. [PortaCount Plus Model 8020 Technical Addendum revised 7-27-2001](https://tsi.com/getmedia/0d5db6cd-c54d-4644-8c31-40cc8c9d8a9f/PortaCount_Model_8020_Technical_Addendum_US?ext=.pdf)
