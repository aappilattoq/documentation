---
layout: default
title: peers
categories: [Reference, Functions, peers]
published: true
alias: reference-functions-peers.html
tags: [reference, communication functions, functions, peers]
---

[%CFEngine_function_prototype(filename, regex, groupsize)%]

**Description:** Returns a list of peers from the partition to which
the current host belongs, excluding the current host.

This function returns a list of hostnames that may be considered peers
of the current host. Peers are defined according to a list of hosts,
provided in `filename`. This file should contain a list (one per line), 
possible with comments matching the [unanchored][unanchored] regular 
expression `regex`, of fully qualified host names. 
CFEngine breaks this list up into non-overlapping groups of up to `groupsize`, 
each of which has a leader that is the first host in the group.

The current host should belong to this file if it is expected to interact with 
the others. The function returns nothing if the current host does not belong 
to the list.

[%CFEngine_function_attributes(filename, regex, groupsize)%]

An arbitrary limit of 64 is set for `groupsize` to avoid nonsensical 
promises.

**Example:**

Prepare:

[%CFEngine_include_snippet(peers.cf, #\+begin_src prep, .*end_src)%]

Run:

[%CFEngine_include_snippet(peers.cf, #\+begin_src cfengine3, .*end_src)%]

Output:

[%CFEngine_include_snippet(peers.cf, #\+begin_src\s+example_output\s*, .*end_src)%]
