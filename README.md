Frege Chat
==========

This application has been developed in preparation of the JavaOne Emerging Languages panel.

Every language has to develop a chat application.

This project implements the Frege variant in an extremely simple fashion where
clients share the state of the chat on a server, post new messages to the server, and
update by requesting the current list of postings.

The server part is implemented with the Chinook library (sparkjava for Frege).

The client part is implemented with FregeFX (JavaFX for Frege).

How to build and run
====================

The build needs the latest snapshot version of FregeFx, so you first need to
build that locally with
> cd my-fregefx-dir
> gradlew install

After that preparation, you can build and run the server with
> gradlew :server:run

(port 8080 should be unused on your machine)


and in a new terminal run clients via
> gradlew :client:run

Any Java version 7, 8, or 9 should be fine.

Known issue
===========

Due to version conflicts between Chinook and FregeFX, the _shared_ module
is only used for the server module (not for both server and client as it should be).
The client module temporarily maintains a copy of the shared "Data" definition.