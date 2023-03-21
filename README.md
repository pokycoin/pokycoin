Pokycoin Core integration/staging tree
=====================================
![dsfsfsfff](https://user-images.githubusercontent.com/125458177/226607730-52d94300-1c3d-44b4-886d-2abe636e81f8.png)


![250](https://user-images.githubusercontent.com/125458177/226606803-4c84dc9a-90ce-4f97-ac8d-6ff62914b5b4.jpeg)![252](https://user-images.githubusercontent.com/125458177/226606829-994ad8a9-c14d-44a3-bf50-b80feab50830.jpeg)


Nodes and pools
---------------

addnode=104.248.116.116

Poky Pool: https://157.230.220.21

What is Pokycoin?
----------------
Just a friendly meme coin

10k Pokys reward per block mined

Pokycoin is an experimental new digital currency that enables instant payments to
anyone, anywhere in the world. Pokycoin uses peer-to-peer technology to operate
with no central authority: managing transactions and issuing money are carried
out collectively by the network. Pokycoin Core is the name of open source
software which enables the use of this currency.



License
-------

Pokycoin Core is released under the terms of the MIT license. See [COPYING](COPYING) for more
information or see http://opensource.org/licenses/MIT.

Development process
-------------------

Developers work in their own trees, then submit pull requests when they think
their feature or bug fix is ready.

If it is a simple/trivial/non-controversial change, then one of the Pokycoin
development team members simply pulls it.

If it is a *more complicated or potentially controversial* change, then the patch
submitter will be asked to start a discussion (if they haven't already) on the
[mailing list](https://groups.google.com/forum/#!forum/pokycoin-dev).

The patch will be accepted if there is broad consensus that it is a good thing.
Developers should expect to rework and resubmit patches if the code doesn't
match the project's coding conventions (see [doc/coding.md](doc/coding.md)) or are
controversial.

The `master-0.10` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/pokycoin-project/pokycoin/tags) are created
regularly to indicate new official, stable release versions of Pokycoin.

Testing
-------

Testing and code review is the bottleneck for development; we get more pull
requests than we can review and test on short notice. Please be patient and help out by testing
other people's pull requests, and remember this is a security-critical project where any mistake might cost people
lots of money.

### Manual Quality Assurance (QA) Testing

Large changes should have a test plan, and should be tested by somebody other
than the developer who wrote the code.
Creating a thread in the [Pokycoin discussion forum](https://pokycointalk.org/index.php?board=2.0) will allow the Pokycoin
development team members to review your proposal and to provide assistance with creating a test plan. 


Translations
------------

**Important**: We do not accept translation changes as GitHub pull requests because the next
pull from Transifex would automatically overwrite them again.

We only accept translation fixes that are submitted through [Bitcoin Core's Transifex page](https://www.transifex.com/projects/p/bitcoin/).
Translations are converted to Pokycoin periodically.

Development tips and tricks
---------------------------

**compiling for debugging**

Run configure with the --enable-debug option, then make. Or run configure with
CXXFLAGS="-g -ggdb -O0" or whatever debug flags you need.

**debug.log**

If the code is behaving strangely, take a look in the debug.log file in the data directory;
error and debugging messages are written there.

The -debug=... command-line option controls debugging; running with just -debug will turn
on all categories (and give you a very large debug.log file).

The Qt code routes qDebug() output to debug.log under category "qt": run with -debug=qt
to see it.

**testnet and regtest modes**

Run with the -testnet option to run with "play pokycoins" on the test network, if you
are testing multi-machine code that needs to operate across the internet.

If you are testing something that can run on one machine, run with the -regtest option.
In regression test mode, blocks can be created on-demand; see qa/rpc-tests/ for tests
that run in -regtest mode.

**DEBUG_LOCKORDER**

Pokycoin Core is a multithreaded application, and deadlocks or other multithreading bugs
can be very difficult to track down. Compiling with -DDEBUG_LOCKORDER (configure
CXXFLAGS="-DDEBUG_LOCKORDER -g") inserts run-time checks to keep track of which locks
are held, and adds warnings to the debug.log file if inconsistencies are detected.
