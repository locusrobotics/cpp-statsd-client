^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package cpp-statsd-client
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

2.4.0 (2025-06-06)
------------------
* Make send thread safe (#53)
* try newer images for ci (#54)
* Fix include install directory (#50)
* Contributors: Aaditya Ravindran, Kevin Kreiser, Paul Bovbel

2.3.0 (2025-02-04)
------------------

2.2.0 (2024-09-16)
------------------

2.1.0 (2024-06-17)
------------------
* Install basic package.xml for rosdep resolve
* Fix include install directory
* Prepare v2.0.1 (#48)
* fix: FreeBSD compile error (#47)
* homepage_url only available in cmake >= 3.12 (#46)
  * this was introduced in cmake 3.12.4.
  * min should be 3.12.4
* feat: support custom metric types (#45)
  Add a `custom()` method where the metric type is passed in by the caller,
  to allow using statsd backends that support metric types beyond those
  supported by the original Etsy statsd daemon.
* Add `-Wsign-conversion -Wsign-promo` compiler flags (#43)
  * Add `-Wsign-conversion -Wsign-promo` compiler flags
  * chore: Update to Visual Studio 22 to match GitHub windows-latest image
  Co-authored-by: David Sze <sze.david@gmail.com>
* feat: bail early if the statsd host is un/misconfigured (#40)
* fixup! docs: update README
* docs: update README
* feat: allow float gauges (#39)
* docs: update linux and windows workflow badges (#38)
* build: only set CXX properties for tests (#34)
* chore: rename workflows files (#37)
* feat: add Windows support (#33)
  Co-authored-by: Rahul Sheth <rahul@snap.com>
* chore: fix typo (#36)
* fix: inline sanitizePrefix (#35)
  If one includes this header in multiple compilation units, one will violate the ODR and the compiler will complain that it is  defined multiple times. Inlining `sanitizePrefix` fixes this issue.
* feat: extend batching controls (#31)
* ci: add code coverage (#32)
* feat: support sets and tags (#30)
* feat: maintain buffer to avoid reallocations (#29)
* feat: automatically add '.' between prefix and key when omitted (#28)
* feat: update cmake (#25)
  Make it easier for downstream applications to depend on the library
* test: add tests using statsd server mock (#19)
* fixup! ci: add lint workflow (#24)
* ci: add lint workflow (#24)
  * add lint workflow + specify clang-format version
  * lint the code
  * remove deprecated travis CI file
  * remove useless git submodule file
  * rename test workflow and trigger on push + pull request
  * fix badges in readme
* feat!: backport to C++11
  Backporting to C++11 will allow more users to adopt the client. The API had to be changed to support this.
* fix: prevent batching thread to run indefinitely when UDPSender is destroyed (#16)
  Make m_mustExit an std::atomic<bool> and use std::memory_order_acq_rel ordering so that other threads are guaranteed to see the change of value of m_mustExit.
* Make function definitions inline
* Fix CI
* Fix CMakeLists in order to be able to perform `make install`
* Use master as default branch
* Contributors: Greg Clark, Greg Knisely, Jeremiah, Kevin Kreiser, Neil Weidinger, Paul Bovbel, Rahul Sheth, Vincent Thiery, dsze, vthiery
