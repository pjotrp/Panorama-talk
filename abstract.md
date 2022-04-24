"Using GUIX for Packaged, Portable, and Reproducible Research in Computer
Architecture"

Outline:

abstract paragraph

1. Challenges in Packaged, Portable, and Reproducible OSS
2. Using GUIX for Packaged, Portable, and Reproducible OSS
3. Case Study: Accelerating Bioinformatics

So section 1 would have an intro paragraph and then lay out three key
challenges (one paragraph each):

1. The OSS Packaging Challenge
 - gem5 rapidly changing, many forks, many compile-time options
 - many versions even in the same gorup
2. The OSS Portability Challenge
 - cross-compiler
 - gem5 uses pre-compiled binaries
 - need to ensure simulator, cross-compiler, app all stay in sync
 - need to use static compilation for syscall emulation
3. The OSS Reproducibility Challenge

The packaging challenge can be about how it is hard to package OSS ...
centralized package repositories, dealing with dependencies, challenges
with both fully source packaging vs precompiled binary packaging, being
tied to a Linux distribution and/or programming language specific
packaging environments. Stuff like that. So this should motivate guix
packages but not focus on cross-compiling or GUIX containers or MES
bootstrapping.

The portability challenge is about how even if you have things well
packaged, these OSS packages are often tied to a specific architecture
and easily porting OSS to other architectures is hard. You need to setup
a cross-compilation toolchain and recompile everything. So this should
motivate the cool "build --target" feature in GUIX.

The reproducibility challenge is about even if you have well packaged and
portable OSS, it can still be hard to reproduce research. We can discuss
why docker isn't the solution and the bootstrapping problem.

Then in Section 2 we have one paragraph to introduce GUIX then we explain
how GUIX addresses each of the challenges (one paragraph each).

1. The OSS Packaging Challenge -> addressed using core GUIX channels,
package, substitutions features?

2. The OSS Portability Challenge -> addressed using build --target,
anything else?

3. The OSS Reproducibility Challenge --> addressed using MES
bootstrapping, manifests, containers?

Then we use the SW on gem5 as the case study. We have an intro paragraph
that sketches out wanting to explore accelerating bioinformatics and the
need for a baseline (i.e., running SW on gem5). Then we have one
paragraph each to illustrate how GUIX addresses the three challenges in
the context of the case study:

1. The OSS Packaging Challenge -> focus on guix package for qemu and gem5
2. The OSS Portability Challenge -> focus on cross-compiling SW
3. The OSS Reproducibility Challenge --> focus on the workflow package
you and Arun are working on + creating a container
