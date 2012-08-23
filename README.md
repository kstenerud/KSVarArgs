KSVarArgs
=========

#### Taking the pain out of variable argument lists in Objective-C.

What Is it?
-----------

A set of macros that hide away the nastiness of va_list and friends, and provide a
simple, block based interface for iterating variable argument lists and for building common collections.


Usage
-----

	#import "KSVarArgs.h"

	- (void) doSomethingWithObjectsAndKeys:(id) firstArg, ...
	{
		// Convert the argument list into a dictionary called
		// "myDict", assuming object, key, object, key, ...

	    ksva_list_to_nsdictionary(firstArg, myDict);
	    NSLog(@"Created dictionary %@", myDict);
	}

	- (void) doSomethingWithArgs:(id) firstArg, ...
	{
		// Convert the argument list into an array called "myArray"

	    ksva_list_to_nsarray(firstArg, myArray);
	    NSLog(@"Created array %@", myArray);
	}

	- (void) printSomeArgs:(id) firstArg, ...
	{
		// Iterate over all arguments, logging each one.

	    ksva_iterate_list(firstArg, ^(id entry) {
	        NSLog(@"Entry = %@", entry);
	    });
	}


License
-------

Copyright (c) 2012 Karl Stenerud

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
the documentation of any redistributions of the template files themselves
(but not in projects built using the templates).

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
