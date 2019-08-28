# Hexagonal Architecture

Hexagonal Architecture or Ports and Adapters is a pattern that promotes decoupling from technology and frameworks.

## The Hexagon

Inside the hexagon we just have the things that are important for the business problem that the application is trying to solve.

The hexagon contains the business logic, with no references to any technology, framework or real world device. So the application is technology agnostic.

Ports & Adapters pattern says nothing about the structure of the inside of the hexagon. You can have layers… you can have components by feature… you can have spagheti code… you can have a Big Ball of Mud… you can apply DDD tactical patterns… you can have a single CRUD… it’s up to you.

## Intent

Allow an application to equally be driven by users, programs, automated test or batch scripts. Allow an application to be developed and tested in isolation from its eventual run-time devices and databases.

As events arrive from the outside world at a port, a technology-specific adapter converts it into a usable message and passes it to the application. The application is blissfully ignorant of the nature of the input device. When the application has something to send out, it sends it out through a port to an adapter, which creates the appropriate signals needed by the receiving technology \(human or automated\). The application has a semantically sound interaction with the adapters on all sides of it, without actually knowing the nature of the things on the other side of the adapters.

* input device =&gt; port =&gt; adapter =&gt; application
* application =&gt; port =&gt; adapter =&gt; output device

## Motivation

Business logic into the user interface code or database. That's mean outside the application.

The system can’t be tested with automated test suites because part of the logic needing to be tested is dependent on user interface It becomes impossible to shift from a human-driven use of the system to a batch-run system It becomes difficult or impossible to allow the program to be driven by another program when that becomes attractive.

Every functionality of the application is available through an API \(application programmed interface\). The business experts can create automated test cases, before the GUI details are finalized, that tells the programmers when they have done their work correctly \(and these tests become the ones run by the test department\).

The rule to obey is that code pertaining to the "inside" part should not leak into the "outside" part.

For each external device there is an "adapter" that converts the API definition to the signals needed by that device and vice versa. A graphical user interface or GUI is an example of an adapter that maps the movements of a person to the API of the port.

On another side of the application, the application communicates with an external entity to get data. The protocol is typically a database protocol. From the application's perspective, if the database is moved from a SQL database to a flat file or any other kind of database, the conversation across the API should not change.

The supposed problem with layered architecture is that it let the application logic leak across the layer boundaries.

## Port

The word “port” is supposed to evoke thoughts of "ports" in an operating system, where any device that adheres to the protocols of a port can be plugged into it; and "ports" on electronics gadgets, where again, any device that fits the mechanical and electrical protocols can be plugged in.

The protocol for a port is given by the purpose of the conversation between the two devices.

The protocol takes the form of an application program interface \(API\).

## References

* [https://alistair.cockburn.us/hexagonal-architecture/](https://alistair.cockburn.us/hexagonal-architecture/)
* [https://softwarecampament.wordpress.com/portsadapters/](https://softwarecampament.wordpress.com/portsadapters/)

