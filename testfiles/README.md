# Test Files - what are they for?

These files allow developing on the scripts without having to have the portacount available to test with.

## Files for `fitconvert`

* Should output TSV: `ascii-fit-test-report-passing-zerocheck-filter-complete.txt` - a full test report of a test of the machine with a zero filter
* Should output TSV: `ascii-fit-test-report-failing-complete.txt` - a full test report of a very badly fit mask
* Should error: `ascii-fit-test-report-failing-fit-test-number-too-high.txt` - a corrupted test report where one of the fit tests had a number of 13, which is out of range
* Should error: `ascii-fit-test-report-failing-fit-test-number-too-low.txt` - a corrupted test report where one of the fit tests had a number of 0, which is out of range
* Should error: `ascii-fit-test-report-failing-incomplete.txt` - a corrupted test report which is missing some of the exercises
