# tis-interpreter

This is [tis-interpreter](http://trust-in-soft.com/tis-interpreter), an interpreter of C for detecting undefined behavior.

tis-interpreter detects subtle bugs in C programs that may not have
eye-visible effects when executing the same programs compiled in the
traditional way. Some of the bugs that are discovered lead to security
vulnerabilities. Fortunately, most don’t.

tis-interpreter works by interpreting C programs statement by
statement from beginning to end, verifying at each statement whether
the program can invoke undefined behavior. This makes it comparable to
Valgrind and C compiler sanitizers (UBSan, ASan, …). The recommended
use is to apply tis-interpreter to existing tests for
security-sensitive C code in which a bug could have dramatic
consequences. tis-interpreter can detect violations of the C standard
even when applied to regression tests that have never revealed any
problem.

At this stage, the best uses for tis-interpreter are pure C libraries with
as few dependencies as possible and existing tests. After compilation
(or after downloading a soon-to-be-available binary package), you can
experiment with [examples of increasing difficulty](https://github.com/TrustInSoft/tis-interpreter/blob/master/tis-interpreter/EXAMPLES.md).

tis-interpreter is based on the open-source [Frama-C platform](http://frama-c.com),
developed by CEA LIST and Inria over the last eleven years. We are
grateful to all Frama-C developers for their contributions to making
formal verification practical in academic and industrial contexts.
