# **MAXINE VM**
- This is the first comprehensive description of the architecture of the Maxine VM, a
VM for Java written in Java.
- We present the design of a tightly integrated VM visualization/debugging tool, useful
for both beginners and experts.
- We describe the annotations, interfaces, and other source-code techniques that make
the Maxine VM approachable.
- We provide a performance evaluation showing that the Maxine VM is robust and
fast enough to serve as a base for research projects.

### Questions
- **metacircular design** - don't understand the meaning of this
- Which GC does it currently use?
- **ReferenceScheme** - why is this useful? How is it used?
- **MonitorScheme** :
> It stores lock ownership information in the object header
using nonblocking atomic instructions when satisfying uncontended lock request. On
contention, the locking information embedded in the object header is converted into
a pointer to an external heavyweight locking data structure that relies on OS mutex
functions to handle contention.

How is it aware if there is contention?
