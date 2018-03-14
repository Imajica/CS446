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

- **Maxine Inspector** - imposes low overhead but can it be disabled if needed?

>Significant complexity in this effort derives from the
circularity
of Maxine’s design.
For example, the Inspector provides access to objects in terms of their
types
,which
requires access to the VM’s metadata, which is also represented in the VM as objects.
Such circularities require a phased approach to construct and maintain
tele
’s model
of runtime state, mirroring in some respects the phased construction needed for the
Maxine boot image generation.



### Answers:
- What is the key point of the paper? (If it is the survey, what are the key techniques it presents?)

The key point of the paper is the Maxine VM for Java. Maxine VM is an open source project written in Java in order to benefit from the high-level language programming.The architecture of the VM is highly modular enabling alternate subsystem implementations to be plugged in. The main focus of the authors is not only the efficiency but also on creating an approachable VM. The approachability features include the Maxine Inspector - a visualizer/debugger for the Maxine VM implementation, Boot Image generation - how Maxine VM is compiled from Java source code to machine code and run using a host VM. Substitution of JDK methods, compiler optimizations and interface, bytecode verification, native interface support and low-level memory access.



- What did you like the most in the paper?


The authors' goal is to create a VM that is approachable to promote the productivity. Productivity is something crucial and yet it is overlooked despite the fact it can be provided with simplicity in most cases. A feature of Maxine VM is the Maxine Inspector which provides information of the VM's runtime state, low-level memory and register contents. Having this tool integrated in the VM helps newcomers to become familiar with the design as the authors claim which I find true. Many times, when undertaking the development of a software project a developer might find the documentation incomplete or hard to understand, so such a tool could be of great help in understanding the design of the VM. Moreover it can also be used for education purposes - something most VM's are not suited for due to the fact that they are not open-source or do not have the approachability features of Maxine VM. An intriguing fact is that the Inspector uses some of the VM code not only design techniques.


- What could be improved in the presentation/content of the paper?

The paper presents the design of the Maxine VM which is a complex software with many modules. I think it would be better if the visualization of the architecture was better, more diagrams and figures that show the VM's modules and their interaction with each other would make it easier for the reader to understand the design of the VM. A better figure for the Inspector should also be provided where the fields of the Inspector are shown and explained. Since the goal of the authors is make an approachable VM the presentation should also be serving the same purpose. However this is a paper that was presented in a conference maybe my suggestions would apply to a simplified version of the paper that would target developers and newcomers.
