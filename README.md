

## Presentations
- https://www.embedded-testing.de/files/embeddedtesting/site/vortraege2019/tag2/Di4.3-Hoer-und-Hartlage.pdf
- [Top N challenges of "deep" fuzzing](https://tinyurl.com/y3znyqls) 
- https://files.meetup.com/17933012/libFuzzer%20-%20May%202016.pdf
- https://i.blackhat.com/USA-19/Wednesday/us-19-Metzman-Going-Beyond-Coverage-Guided-Fuzzing-With-Structured-Fuzzing.pdf
 
## Papers
Recent Papers Related To Fuzzing [link](https://wcventure.github.io/FuzzingPaper/)

- Driller: Augmenting Fuzzing Through Selective Symbolic Execution [paper](https://sites.cs.ucsb.edu/~vigna/publications/2016_NDSS_Driller.pdf)
- QSYM: A Practical Concolic Execution Engine Tailored for Hybrid Fuzzing [[source](https://github.com/sslab-gatech/qsym#run-hybrid-fuzzing-with-afl|[paper](https://www.usenix.org/system/files/conference/usenixsecurity18/sec18-yun.pdf))]
- SymCC: efficient compiler-based symbolic execution [[source](https://github.com/eurecom-s3/symcc)|[slide](https://www.usenix.org/system/files/sec20_slides_popelau.pdf)|[paper](https://www.usenix.org/conference/usenixsecurity20/presentation/poeplau)]
- Device-agnostic Firmware Execution is Possible: A Concolic Execution Approach for Peripheral Emulation [link](https://openreview.net/pdf?id=rylaZ6iIDr)
- Hybrid Fuzz Testing: Discovering Software Bugs via Fuzzing and Symbolic Execution [thesis](http://reports-archive.adm.cs.cmu.edu/anon/2012/CMU-CS-12-116.pdf)


To be explored:

- SAVIOR Fuzzer [source](https://github.com/evanmak/savior-source)
- ParmeSan: Sanitizer-guided Greybox Fuzzing [source](https://github.com/vusec/parmesan)

Other resources:

- https://githubz.com/topics/afl


## Libfuzzer
- [Improving your fuzzer](https://fuchsia.dev/fuchsia-src/development/testing/fuzzing/improve-a-fuzzer)
- https://github.com/google/fuzzing/blob/master/docs/structure-aware-fuzzing.md
- https://forallsecure.com/blog/learning-about-structure-aware-fuzzing-and-finding-json-bugs-to-boot
- https://llvm.org/docs/LibFuzzer.html
- [Fuzzing floating point code](https://rigtorp.se/fuzzing-floating-point-code/)
- https://llvm.org/devmtg/2017-10/slides/Serebryany-Structure-aware%20fuzzing%20for%20Clang%20and%20LLVM%20with%20libprotobuf-mutator.pdf
- https://files.meetup.com/17933012/libFuzzer%20-%20May%202016.pdf
- https://source.android.com/devices/tech/debug/libfuzzer
- https://llvm.org/docs/LibFuzzer.html#:~:text=LibFuzzer%20is%20linked%20with%20the,to%20maximize%20the%20code%20coverage.
- https://www.wolfssl.com/wolfssl-and-libfuzzer/
- https://meetingcpp.com/mcpp/slides/2018/Structured%20fuzzing.pdf


## AFL

### Resources
- https://afl-1.readthedocs.io/en/latest/user_guide.html
- https://x9security.com/fuzzing-explained-with-afl/
- https://blog.f-secure.com/super-awesome-fuzzing-part-one/
- https://foxglovesecurity.com/2016/03/15/fuzzing-workflows-a-fuzz-job-from-start-to-finish/
- https://i.blackhat.com/us-18/Wed-August-8/us-18-Li-AFLs-Blindspot-And-How-To-Resist-AFL-Fuzzing-For-Arbitrary-ELF-Binaries.pdf
- [Fuzzing the Solidity Compiler](https://f.hubspotusercontent20.net/hubfs/7466322/FuzzCon%20Europe%202020%20Slides/Slides%20-%20Bhargava%20Shastry%20-%20Fuzzing%20Solidity.pdf)



## Interesting Blog Post
- https://salvatoresecurity.com/fun-with-fuzzers-or-how-i-discovered-three-vulnerabilities-part-1-of-3/

## Protobuf Mutator
For structure data mutation in structure aware fuzzing. It can be used with LibFuzzer and AFL++.

### Resources
- https://github.com/bruce30262/libprotobuf-mutator_fuzzing_learning/blob/master/2_libprotobuf_libfuzzer/lpm_libfuzz.cc
- https://awesomeopensource.com/project/bruce30262/libprotobuf-mutator_fuzzing_learning
- https://github.com/thebabush/afl-libprotobuf-mutator
- https://github.com/google/libprotobuf-mutator
- https://github.com/leimao/Protocol_Buffer_Examples/blob/master/protos/addressbook.proto
- https://github.com/google/libprotobuf-mutator/blob/master/src/mutator_test.cc
- https://doss-gitlab.eidos.ic.i.u-tokyo.ac.jp/sneeze/chromium/blob/master/testing/libfuzzer/libprotobuf-mutator.md
- https://securityboulevard.com/2020/08/learning-about-structure-aware-fuzzing-and-finding-json-bugs-to-boot/
- https://github.com/google/fuzzing/blob/master/docs/structure-aware-fuzzing.md
- https://googleprojectzero.blogspot.com/2019/12/sockpuppet-walkthrough-of-kernel.html
- https://bshastry.github.io/2019/01/18/Deconstructing-LPM.html
- https://bshastry.github.io/2019/12/27/Custom-Proto-Mutation.html
