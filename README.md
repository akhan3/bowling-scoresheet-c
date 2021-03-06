# bowling-scoresheet-c
A C program to keep score in bowling as the frames are rolled


=========================
Compilation and Usage
=========================
make clean
make

./bowling --help or -h displays help and usage notes.
These are also repeated below.

    Usage: ./bowling [-g [RANDOM_SEED]]
    Notes:
    If run without arguments, the program will read the rolls from stdin and
    display the score on stdout.
    If run with -g argument, the program will only generate valid random rolls
    on stdout that may be redirected as its input in a separate run, like,
    ./bowling < ./bowling -g
    ./bowling -g | ./bowling
    If no seed is given, default will be current time.

Instructions to input data on stdin is also provided during the program run and
is repeated below.

    Enter number of pins knocked down on each valid roll.
    They may be entered either one-by-one or as space separated numbers.
    Important: 0 for the second roll of a strike frame must not be entered
    at all, since it is not a valid roll.
    Some debugging output will be written on-the-fly on stderr.

The program will not accept invalid values of rolls that exceed the number of
currently available pins, and will loop forever until a valid vlaue is given.
Likewise, if there is not sufficient data available for all the rolls till the
end, the program will issue FATAL ERROR warnings and the final scores will not
be valid.

=========================
Test data
=========================
There are many test data files available in the testdata/ directory.
Use for example, ./bowling < testdata/rolls_3strikes.dat
Verification of the output was done against manual calculations as well as
the applet at http://public.csusm.edu/veres/
Since the program writes only final cumulative scores of 10 frames on stdout,
they can be easily verified against your reference score data files using diff
command.

=========================
Additional Information
=========================
The source code is never hard-coded except rolls_per_frame. This could also have
been soft-coded but the required effort was not justified for this simple two
rolls game. This is a work-to-do for future improvements.
