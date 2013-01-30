Couchbase for Mobile
======

Sync JSON documents between Couchbase Server, iOS and Android

## What is it?

Couchbase for Mobile extends Couchbase Server in the cloud with the capability to synchronize with embedded databases on iOS and Android. It targets interactive multi-user applications which need to run reliably, offline or on. These mobile apps can share data or store it privately, and can download manageable subsets of large databases.

Couchbase for Mobile is made up of a handful of components, some in the cloud or your datacenter, others on mobile devices. Here's an architecture diagram.

![Couchbase Mobile Architecture](http://jchris.ic.ht/files/slides/mobile-arch.png)

The components are fairly independent, and require a little bit of elbow grease to create a full deployment, but we've built it that way for flexibility, and so we can take advantage of the stable, GA release of [Couchbase Server 2.0](http://www.couchbase.com/couchbase-server/overview), among other things. Here's a breakdown of the components:

* [Couchbase Server 2.0](http://www.couchbase.com/couchbase-server/overview) -- High performance scalable NoSQL storage that's been battle-tested in heavy-traffic mission critical deployments serving millions of users.
* [TouchDB](https://github.com/couchbaselabs/TouchDB-iOS) -- A NoSQL database for iOS or [Android](https://github.com/couchbaselabs/TouchDB-Android) that provides a native API as well as robust synchronization capabilities using a standard Apache CouchDB-compatible replication protocol.
* [Sync Gateway](https://github.com/couchbaselabs/sync_gateway) -- Interposed between server and client, it handles access control and synchronization, so that a single large Couchbase Server cluster can manage data for multiple users and complex applications.
* **Your Application** -- Couchbase Mobile delegates responsibility for data access control to your code. For each document, you specify which channels it belongs to, and for each user or device, which channels they can see.

## Roadmap

While the Couchbase Server and [TouchDB-iOS](https://github.com/couchbaselabs/TouchDB-iOS/wiki/TouchDB-In-The-Wild) components are already in production, the other components are brand new, so the big picture is **experimental**.

We are actively seeking feedback from users and customers. Please [join our mailing list](https://groups.google.com/forum/#!forum/mobile-couchbase) to discuss improvements, report bugs, or get help with your applications.

## Getting Started

We are putting together example applications and getting started guides. Currently we have an iOS and and HTML5 example. The HTML5 example also includes a node.js application to handle access control.

* iOS -- [TouchWiki-iOS](https://github.com/couchbaselabs/TouchWiki-iOS) is an iPad wiki that uses Markdown format.
* HTML5 for iOS -- [TouchGap](https://github.com/couchbaselabs/TouchGap) is a generic container for PhoneGap applications that can access the data via the TouchDB ReST abstraction at `http://localhost.touchdb./mydatabase`. Check out the README to get started with an example photo chat app that shows off the full Couchbase Mobile authentication flow.

We plan to make an HTML5 version of the wiki, which can run on devices as well as in a browser, for maximum data access.

## FAQ

**Q: Is this the same thing as Syncpoint?**

A: No; Syncpoint was an earlier prototype that had similar goals but a different architecture. Couchbase Mobile takes advantage of Couchbase Server for scalability and provides a simpler model for developers.

**Q: Wasn't "Couchbase Mobile" the old Erlang-based mobile database before TouchDB?**

A: Yup. But it's a good name so we're repurposing it.

**Q: What about Android?**

A: TouchDB for Android is stable enough to be used by some apps already, but it does not yet have the latest features for integration with Couchbase Mobile. We are working on it.

**Q: Will Couchbase Mobile work with Apache CouchDB servers?**

A: No. The Sync Gateway server has custom functionality for access control and aggregation that isn't available in Apache CouchDB.

**Q: What about my existing mobile app that uses TouchDB to sync with Apache CouchDB?**

A: No problem! TouchDB's sync protocol will remain compatible with Apache CouchDB's, so your app will continue to work. If you later need the capabilities of Couchbase Mobile, you can make minor changes to the mobile app to switch to it.
