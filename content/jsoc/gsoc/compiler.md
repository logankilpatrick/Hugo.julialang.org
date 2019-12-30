---
layout: single
title:  Compiler Projects – Summer of Code
---

# {{< get_param title >}}

## Thread-safety

There are many remaining components that need to be updated to use thread-safe algorithms before Julia's threading will be stable for general usage. Some basic data-structures (such as the TypeMap) are missing correct RCU and memory barriers to ensure race-free answers. IO is also currently unavailable for multi-threaded code. The `realloc` operation for arrays (i.e. `resize!`) may be more reliable if it was implemented using RCU `malloc` (delaying the free until a gc-safepoint has been reached on all threads).

**Expected Results**: Demonstrate that a program that fails at the beginning of the summer can now run to completion, or show what remains to be fixed to get it working. Start a test framework to help find bugs and race conditions in the current implementation, and to detect future regressions in multi-threading behavior.

**Recommended Skills**: Experience with thread-safety in C.

**Mentors**: [Jameson Nash](https://github.com/vtjnash)


## Data Structure Algorithm Improvements

Julia is distributed with well-validated implementations of the standard suite of data-structures.
However, there are a range of projects that could be done to improve the quality, performance, or usability of these builtin structures.
Some ideas include:

- Changing Base.Dict to an ordered dict representation (https://juliacollections.github.io/DataStructures.jl/latest/ordered_containers/, https://github.com/JuliaLang/julia/pull/10116)
- Experiment with using alternative Dict hash structures (such as Robin Hood Hashing, used by [Rust](https://doc.rust-lang.org/beta/std/collections/struct.HashMap.html))
- Implementation and tests for assorted asynchronous, threaded storage primitives and data channels
- Array growth-rate parameter
- Using immutable collections (https://github.com/JuliaCollections/FunctionalCollections.jl) to accelerate computational problems in the compiler

But this just a sample list, and is far more than one summer of work. So what do you want to work on?

**Recommended Skills**: Ability to write type-stable Julia code. Ability to find performance issues. Knowledge about data structures and related algorithms. Interest in a particular problem above (or propose your own).

**Contact:** [Jameson Nash](https://github.com/vtjnash)


## Calling Julia from Python

Julia could be a great replacement for C in Python projects, where it can be used to speed up bottlenecks without sacrificing ease of use. However, while the basic functionality for communicating with Julia exists in [PyCall.jl](https://github.com/JuliaPy/PyCall.jl) and [pyjulia](https://github.com/jakebolewski/pyjulia), it needs to be separated out and maintained as a real Python package.

**Expected Results**: An easy-to-use Python package which allows Julia functions to be imported and called, with transparent conversion of data.

**Recommended skills**: Familiarity with both Python and Julia, especially C interop.

**Mentors**: [Steven Johnson](https://github.com/stevengj)


## Calling Julia shared libraries from Python

Similar to the above, but involving [PackageCompiler](https://github.com/JuliaLang/PackageCompiler.jl) to remove JIT overhead.
The successful candidate will start off from the [prototype](https://github.com/JuliaLang/PackageCompiler.jl/pull/26)
and will make sure that linking a shared Julia library to Python works on all platforms.
If there is still time after this, the project can be extended to make the interaction
between Python and Julia work smoothly.
We will need to make sure that all functions can be called with rich
python datatypes, and that conversions to common Julia datatypes happens automatically.
If the conversion can't happen automatically, we need to make sure that there are easy ways
to convert a Python object to the correct Julia object.

**Recommended skills**: This project will require strong knowledge about compiling and linking binaries.
**Expected Results**: An easy way to call into static julia libraries without JIT overhead and with automatic type conversions.

**Mentors**: [Simon Danisch](https://github.com/SimonDanisch/)
