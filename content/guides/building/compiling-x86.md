+++
type = "article"
title = "Compiling Haiku for x86"
date = "2012-09-09T15:36:52.000Z"
tags = ["compiling. x86"]
+++

<h3>x86 Compiler Toolset</h3>
<p>Building the x86 compiler toolset is quite easy and involves generating gcc binaries for your platform. For a complete list of flags for the configure script, see <a href='/guides/building/configure'>Haiku's Configure Options</a></p>
<p>From the haiku source directory, run the following. (be sure to adjust the options to match your build environment.)
<h4>gcc2</h4>
<p>gcc2 is the default build planned for R1 given it's BeOS binary compatibility enabling native binary BeOS applications to run on Haiku.
<pre class="terminal">./configure --build-cross-tools x86_gcc2 ../buildtools</pre></p>

<h4>gcc4</h4>
<p>gcc4 is the default build planned for post-R1. gcc4 doesn't offer complete BeOS binary compatibility, however benefits from using a more-modern toolchain.
<pre class="terminal">./configure --build-cross-tools x86 ../buildtools</pre></p>

<h4>gcc2h / gcc4h hybrid builds</h4>
<p>Haiku can be build as a hybrid image meaning that it contains gcc2 as well as gcc4 binaries. More information on this can be found on the <a href='/guides/building/gcc-hybrid'>gcc-hybrid</a> page.</p>

<h3>x86 Haiku Builds</h3>
<p>These builds require a valid x86 compiler toolset (see above), and might also need additional software packages installed -- see the <a href="/guides/building/pre-reqs">pre-requisite software</a> page for more details.

<h4>Compiling a basic raw Haiku disk image</h4>
<p>This is the most basic build, it generally is good for quickly testing the OS after making modifications as it doesn't contain a lot of extra applications. Be sure to modify -j2 with the number of cpu cores on your build system to ensure the fastest build times.
<pre class="terminal">jam -q -j2 @image</pre>
</p>

<h4>Compiling raw nightly disk images</h4>
<p>This is the default nightly image build target. This contains a complete system with an included compiler. Be sure to modify -j2 with the number of cpu cores on your build system to ensure the fastest build times.
<pre class="terminal">jam -q -j2 @nightly-raw</pre>
</p>