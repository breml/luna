luna [![Build Status](https://travis-ci.org/beatgammit/luna.png)](https://travis-ci.org/beatgammit/luna)
====

Luna is more than a wrapper, it's what a Lua API should be.

There's no more pushing things onto the stack or popping them off; Luna takes care of all that. Lua is fun again:

Define a library:
-----------------

	l := luna.New(luna.AllLibs)
	libMembers := []luna.TableKeyValue{
		{"doStuff", DoStuff},
		{"doThings", DoThings},
		{"makeMeASandwitch", MakeMeASandwitch},
	}
	l.CreateLibrary("lib", libMembers...)

Call a function:
----------------

	l := luna.New(luna.AllLibs)
	l.LoadFile("fun.lua")
	l.Call("awesomeFunction", 3, 4)

install
=======

    go get github.com/beatgammit/luna

Luna uses [golua](https://github.com/aarzilli/golua), and that looks for a shared object called lua5.1 on Linux.

examples
========

Examples are found in `examples/`:

* `helloworld`- loads a file and returns a string; nothing fancy
* `call-function`- make calls from Go -> Lua
* `library`- define library to make calls from Lua -> Go
* `stdout`- override stdout for calls to print()
