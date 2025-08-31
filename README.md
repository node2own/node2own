# Node to Own

_Infrastructure for local-first applications_

Local-first applications are different from client-server applications in that the running process and the data reside on the local device, rather than on someone else's computer.[[1]](#1)

In a client-server app there are two type of nodes:

* Client-nodes run a web-browser that allows the user to interact with the application
* Server-nodes run the actual software, provide long-term storage for the user's data and are totally in control of everything (well nearly everything; nothing is perfect)

In a local-first app there is just one type of node, and it is owned by the user. You can inspect its data, restrict its access to other resources, stop it, delete it. You're back in control.

There should be local-first options for commodity software like
* Sending messages
* Editing documents
* Organizing lists
* Organizing finances (spreadsheets)
* (Video) calling people
* Making presentations

This needs to be facilitated by infrastructure. Ideally the existing infrastructure for client-server applications can be re-used for local-first applications. However, to make local-first nodes just as powerful as server nodes, two problems must be solved:

* [Peer-to-peer communication](peer-to-peer/README.md)
* Collaborative persistence

The solutions to these problems are likely to be interdependent. Peer-to-peer communication will rely on collaborative persistence to exchange information on where to reach other nodes. Collaborative persistence will rely on the ability to exchange events with other nodes over peer-to-peer channels. Therefore, it might be advantageous to use a few servers initially, to bootstrap the network. After a while, however, it should be possible to use the full functionality of local-first applications without the need for any type of server.

----

#### [1]

["There is no cloud, it’s just someone else’s computer"](https://medium.com/@brian.greenberg/there-is-no-cloud-its-just-someone-else-s-computer-fe8b62a027a5)
