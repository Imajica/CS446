# **MAXINE VM**
- This is the first comprehensive description of the architecture of the Maxine VM, a
VM for Java written in Java.
- We present the design of a tightly integrated VM visualization/debugging tool, useful
for both beginners and experts.
- We describe the annotations, interfaces, and other source-code techniques that make
the Maxine VM approachable.
- We provide a performance evaluation showing that the Maxine VM is robust and
fast enough to serve as a base for research projects.

### Questions:
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

> Code pointers are distinguished from object references
and known to the optimizing compiler, which produces separate reference maps for
pointers to compiled code on the stack

- **Boot Image generation** Maxine VM is said to replace HotSpot VM however it uses the HotSpot VM for the boot image generation?

>The T1X baseline compiler is Maxine’s first line of execution (Maxine has no inter-
preter)

- That is bizarre.

### Answers:
- What is the key point of the paper? (If it is the survey, what are the key techniques it presents?)

The key point of the paper is the Maxine VM for Java. Maxine VM is an open source project written in Java in order to benefit from the high-level language programming.The architecture of the VM is highly modular enabling alternate subsystem implementations to be plugged in. The main focus of the authors is not only the efficiency but also on creating an approachable VM. The approachability features include the Maxine Inspector - a visualizer/debugger for the Maxine VM implementation, Boot Image generation - how Maxine VM is compiled from Java source code to machine code and run using a host VM. Substitution of JDK methods, compiler optimizations and interface, bytecode verification, native interface support and low-level memory access.
- What did you like the most in the paper?  
The authors' goal is to create a VM that is approachable to promote the productivity. Productivity is something crucial and yet it is overlooked despite the fact it can be provided with simplicity in most cases. A feature of Maxine VM is the Maxine Inspector which 
