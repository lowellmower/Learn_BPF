# Overview
#### Background, Vernacular, and Lexicon

This section is intended to give a reasonable level of depth and breadth to establish our BPF learning on
top of. I imagine this seciton to be a continued work in progress which will be added to and emmended as
necessary. For the immediacy however, this section will provide some common terminology and background so
that we may have shared language to discuss and explore BPF and the surrounding ecosystem.

A vast majority of this will be driven and guided in ways based on Brendan Gregg's wonderful introduction
to the topic, [BPF Perfomrance Tools Linux System and Application Observability](http://www.brendangregg.com/blog/2019-07-15/bpf-performance-tools-book.html).

## Background
### BPF History to Today

BPF was originally design specifically for the Berkely Software Distribution (BSD) operating system. Seems
obvious, no? [It was introduced in 1992 in a paper](http://www.tcpdump.org/papers/bpf-usenix93.pdf) about
the architecture surrounding packet capturing at the user level, specifically with respect to the througput
of UDP/IP packets on the DECstation 5000. This original implementation was relatively straight forward, 
[BPF byte code](./lexicon.md#bpf-byte-code) was used to define a set of filter instructions and loaded into
the kernel. All packets coming in from network devices would then have these filters applied before being
returned up to user space by the implementing program (think tcpdump).

This original implementation consisted only of two registers, a scratch memory store with 16 slots, and a
program counter all operating under a 32-bit register. It wasn't until 1997 that this version of BPF would
land in the Linux kernel (v 2.1.75).

A little over a decade later (2011), Eric Dumazet (currently of Google), added the JIT compiler which would
land in kernel version 3.0. There continued to be some notable improvments there as Gregg's book covers in
more detail than I intend to do here. If you're at all curious, I thoroughly encourage you to purchase and
read that publication.

It seems the tipping point for the adoption of BPF was Alexi Starovoitov's introduction of Extended Berkely
Packet Filter (eBPF) which ushered in a wealth of contributors, tools, and accessibility to the ecosystem.
eBPF increased the register count from 2 to 10, added support for 64-bit widths, allocated 512 bytes of stack
space, and opened up the event targets beyond packet filtering. These changes (among other notable ones such
as map storage) ignited innovation with and adoption of BPF as a technology which could bridge the gap between
user space and the kernel in a safe and accessible way.

Generally, BPF now refers to this "extended" world and makes no distinction (unless necessary) between classic
BPF and eBPF.

## Lexicon

I'm a firm believer in specific language, especially and specifically in relationg to complex topics. Words
matter greatly and having a solid understanding of the vernacular specific to a topic is a part of mastering
the subject. As acronyms and terminology come up, it is my intention to continue to build out the lexicon 
accompanying this repository. Some topics may require extended explanation and may result in a deeper dive or
associated write up.

- [See Lexicon Section](./lexicon.md)
