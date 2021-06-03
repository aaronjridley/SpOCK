### This is a document used solely for code maintenance by the original program authors and should be considered read-only by the user.
### Last Updated: 3nd June 2021 by A. Kingwell


## Section 1: The load_options() Function

### General Purpose of load_options() Function
The load_options() function, contained within the load_options.cpp file, is used to provide the user a way to select their desired debug level,
the aspects of spacecraft body, and the space environment physics that they desire to work with. Aspects of SpOCK functionality modified or 
"set" in this function include SPICE options, timekeeping and date settings, physics and orbit, options for the output from the program the 
user desires, and others.


### Rough Order of Tasks Performed by load_options() Function
(1) Variable initialisation: Around 150 variables are declared, including for-loop iterators and ones used as temporary placeholders. A. Ridley
	has said this style is probably due to the original author's familiarity with FORTRAN.

(2) File read-in: The program attempts to open and read the options input file given by the user. If the file cannot be opened or read the 
	program prints a debug message and terminates.

(3) The program first searches for the first set of options in the user's file. If this section cannot be found, the program terminates.

(4) The program uses primarily the strcpy() and strcat() functions to store information from the user's file into the pre-declared variables.

(5) This process is repeated for many different aspects of the space and simulation environment, and spacecraft body. These tasks are separated 
	roughly by existing comments in the original code but are somewhat ambiguous in a few places. In all cases, the program prints a debug 
	message and then terminates if it encounters a file which it cannot read or a file which does not contain the expected information.


### Unique Features of load_options() Function
The load_options() function does not have many comments in general, and it is also very long. As such the complete set of actions performed
by this function may not conform exactly to the process described above and will not be fully documented until re-appraisal is complete.  

The load_options() function contains substantial sections of code that have been commented out with no accompanying comments to indicate why
this code is no longer included.

