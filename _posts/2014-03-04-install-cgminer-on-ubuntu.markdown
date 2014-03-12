---
layout: post
title:  "Install CGMiner on Linux for Scrypt mining"
summary: "How to install CGminer binary for Ubuntu"
date:   2014-03-04 20:20:26
permalink: /guides/install-cgminer-on-ubuntu.html
categories: guides
guideid: 1
---

Get started with GPU mining  using the latest version of CGminer that supports the Scrypt algorithm.

The first step is to install the dependencies and extra goodies to make our life easier.

<pre>
  <code class="language-bash">
    $ sudo apt-get install build-essential cdbs dh-make dkms execstack dh-modaliases linux-headers-generic fakeroot libqtgui4 lib32gcc1 zlib1g-dev libssl-dev libreadline-gplv2-dev libyaml-dev dpkg-dev libcurl4-gnutls-dev libncurses5-dev libtool wget openssh-server screen
  </code>
</pre>

The next step is to install CGMiner 3.7.2 which is the last of breed to support Scrypt algorithm. We are going to create a `mine` directory in our user's home `~/mine` and change directory to our newly created `mine` directory.

<pre>
  <code class="langauge-bash">
    $ mkdir -p ~/mine && cd ~/mine
  </code>
</pre>

Now we will download the CGMiner 3.7.2 binary to our `~/mine` directory.

<pre>
  <code class="languague-bash">
    ~/mine$ wget http://ck.kolivas.org/apps/cgminer/3.7/cgminer-3.7.2-x86_64-built.tar.bz
  </code>
</pre>

Once downloading is complete, let's create a `cgminer` directory and extract the `cgminer-3.7.2-x86_64-built.tar.bz` archive.

<pre>
  <code class="languague-bash">
    ~/mine$ mkdir -p ~/mine/cgminer && tar xvf cgminer-3.7.2-x86_64-built.tar.bz2 -C cgminer --strip-components 1
  </code>
</pre>

Fin. Congratulations! You are now setup with CGMiner and can mine away by running the `./cgminer` binary from the CGMiner directory: `cd ~/mine/cgminer/`.

<pre>
  <code class="languague-bash">
    ~/mine/cgminer$ ./cgminer -o stratum+tcp://server:port-number -u worker.username -p password
  </code>
</pre>
