<!--This template should be copied to a file named after the pep -->
\<Additional Node Scope\>
==========================

Proposal
==========================
Create a new level of scoping, in between top scope and class scope.

Purpose & Background
==========================
While investigating [#1372](https://projects.puppetlabs.com/issues/1372) I 
realized that the only sane solution to this and the related set of bugs was to
introduce a new scope, existing between top scope and node scope.

Currently, the scope created by a node definition is treated like a class, and
loaded into the same level of scope. As such, if you have a node that has the
same name as a class, the class will not always get included as expected.