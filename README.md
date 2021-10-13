# libidevice

A Rust re-imaging of `libimobiledevice`

## Why do this?

We depend on `libimobiledevice` today to break Apple monoculture and therefore half of the iOS / Android duopoly.  Because restoring a device to a known good state is fundamental to computer security today (think two factor tokens and password managers) we need clean, highly secure code paths to device measuremnt and restore.

## Why not `go-lang`?

Completely honest?  Because building iDevice bindings in a language primarly owned by the other half of the duopoly feels like unhitching from one crazed horse and latching to the other...

Rust has seen parts of the linux kernel become developed so it has a track record of distributed design and high levels of C interoperability.  Rust feels like the right choice for a type safe, cross platform library these days.

## Why not C++?

C++ (espically modern C++) is an attractive choice.  It reduces the amount of marshaling that has to be done including the unwinding of if blocks for error checking and the containment of related functions and state.  Unfortuantly C++ has a bad wrap, in part due to symbol mangling.  Because of the symbol mangaling (the wildly long and complex function names which include type information to ensure that overlaodign can occur) it is extemely diffuclt to interoperate with a C++ library, via ways of like `libffi`.  Therefore by going to C++ we would loose the universal nature of being able to be called by almost any high level language
