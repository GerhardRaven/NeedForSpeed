NeedForSpeed
============

Fast or not? Collective wisdom on what is faster than other things.

This is a collection of recipes/dirty tricks for how to write C++11
code which will run fast. Some will be examples of how _not_ to do it.
Some will show that it does not matter what you do.

The aim is to provide a library of examples that can be consulted for
enlightenment.


Binary searches
===============

searching.cpp compares three different way of finding the first
element larger than X in a vector. Compile it with:

```
for d in FIND STD SELF; do
  clang++ -std=c++11 -stdlib=libc++ -O3 searching.cpp -D$d -o search_$d.x;
done;
```

This creates three executables one for each method. The three methods
are a home made binary search, std::lower_bound and std::find_if.


Timers
======

timing.cpp is an example of how to measure the passage of time. Benchmarks
all require some kind of time measurement. The more precise the clock
the better. Though there are a lot of pitfalls when it comes to building
a good benchmark, especially when it is a micro-benchmark.

```
clang++ -std=c++11 -stdlib=libc++ -O3 timing.cpp -o timing.x;
```

The timers which are part of the C++11 standard library are pretty good!