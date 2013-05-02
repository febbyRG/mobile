Couchbase Mobile
======

Sync JSON documents between Couchbase Server and Couchbase Lite on iOS and Android.

## Why Sync?

Syncronization is the future of mobile data. Users love services like Dropbox, because they know they can access their data no matter what, even if they are offline or on a slow network. The reliability and performance of data stored on your device can't be beat by any remote storage. The advantages to sync are so strong that even Apple is getting into the game with iCloud.

Neither Dropbox or iCloud really offer what developers want. Dropbox is for files, not application data, so while you can jump through hoops to sync a database file with it, as soon as you have more than one user editing the same data at the same time, all bets are off. iCloud, even on it's best days, doesn't give developers much access to query over the complete data their application has generated. Without this sort of access, it's hard to discover user trends, or provide aggregations either to your business or to your users.

Couchbase Lite speaks an [industry standard, proven synchronization protocol](https://github.com/couchbase/couchbase-lite-ios/wiki/Replication-Algorithm). It's native on iOS and Android, so it's lightweight optimized for app download and launch time. Quit agonizing over network reachability errors and focus on adding value to your application.

## Mobile Tech Stack

Couchbase Lite enables sync on your handset, and includes a sync gateway in the download to handle the server side of your sync apps. In production you'd run the sync gateway using Couchbase Server for storage, so you can handle a growing userbase with confidence.

![Couchbase Mobile Architecture](http://jchris.ic.ht/files/slides/mobile-arch.png)

* [Couchbase Server 2.0](http://www.couchbase.com/couchbase-server/overview) -- High performance scalable NoSQL storage that's been battle-tested in heavy-traffic mission critical deployments serving millions of users.
* [Couchbase Lite](https://github.com/couchbase/couchbase-lite-ios) -- A lightweight NoSQL database for iOS or [Android](https://github.com/couchbaselabs/TouchDB-Android) that provides a native API as well as robust synchronization capabilities using the standard Apache CouchDB-compatible replication protocol.
* The [Sync Gateway](https://github.com/couchbaselabs/sync_gateway) manages HTTP-based data access for mobile clients. It handles access control and data routing, so that a single large Couchbase Server cluster can manage data for multiple users and complex applications.
* **Your Application** -- Your application has fine-grained control over data access and routing. For each document, you specify a set of [channels it belongs to, and for each user or device, you control which channels they can see.](https://github.com/couchbaselabs/sync_gateway/wiki/channels-access-control-and-data-routing-w-sync-function)

## Use Cases

We've been working with community users and customers on use cases like this:

* Medical Records - this data is a great fit for schemaless JSON storage. It's also critical that it be available wherever the health care provider goes, regardless of network conditions.
* Customer Loyalty and Point of Sale - we see a lot of these apps already using our sync technology, and we've been working with some developers closely to ensure a smooth ride.
* Airline - pilots and flight attendants benefit from having easy access to data about passengers and flight plans, with the ability to dynamically refresh the data when they are on the ground.
* Fleet Management - tracking vehicle telemetry and routing it to the cloud when connections are available is a great fit for Couchbase Mobile
* Social Media - chat and game companies often take a portfolio approach. By offloading the details of pushing data across mobile networks, they can focus on rolling out compelling content that utilizes a common backbone.

## Get Started w/ Tutorials

As of April 2013 we have example code for native iOS applications, and for HTML5 PhoneGap / Cordova apps on iOS. We'll be bringing our Android examples and tutorials up to parity in the next few months. There are also a lot of older examples out there. We'd like to bring them all up to date over time, but for now we are focussing on making a few of them really easy to follow. Watch this list to see what's available as we expand our supported tutorials.

### Native iOS

The native iOS chat application, [CouchChat-iOS](https://github.com/couchbaselabs/CouchChat-iOS), illustrates how users can dynamically create channels and invite other users to join them. You should probably skim the README of this app even if you plan to start with the PhoneGap tutorial, because it covers the server-side data routing and access control in more detail.

### PhoneGap / Cordova

The HTML version of the chat application uses the same data structures, and is designed to interoperate with the native version of the app. So you should be able to chat with groups of people who are using both the HTML5 and the native version. Because the data structures are the same, this example doesn't include the server-side SyncGateway configuration. Instead it explains how to use the configuration that is part of the CouchChat-iOS repo, as the backend for your HTML5 data sync.

Here are [instructions to build a PhoneGap container](https://github.com/couchbaselabs/LiteGap/wiki/Building-a-PhoneGap-Couchbase-Lite-Container) and a link to the [PhoneGap Chat example](https://github.com/couchbaselabs/CouchChat-PhoneGap).

## Roadmap

We are currently producing nightly and stable builds of the various components (linked from their individual READMEs). We plan to push out an initial preview release of the server side and iOS client side components in May, and then to do another preview release including the Android client this summer, before going Beta in the fall. After that we'll make a beeline for a GA release so that we can start officially supporting people with mission-critical use cases.

For a detailed look at what we are working on, the issues list on [Couchbase Lite iOS](https://github.com/couchbase/couchbase-lite-ios/issues) and [Sync Gateway](https://github.com/couchbaselabs/sync_gateway/issues) is the place to go. Broadly speaking, between now and GA we are working on security, stability and scalability, with only a few new features planned. This means you should be able to start developing today and transition to the Beta and GA releases without making big changes to your code.

As always, we are actively seeking feedback. Please [join our mailing list](https://groups.google.com/forum/#!forum/mobile-couchbase) to discuss improvements, report bugs, or get help with your applications.


## FAQ

**Q: Is this the same thing as Syncpoint?**

A: No; Syncpoint was an earlier prototype that had similar goals but a different architecture. Couchbase Mobile takes advantage of Couchbase Server for scalability and provides a simpler model for developers.

**Q: Wasn't "Couchbase Mobile" the old Erlang-based mobile database before TouchDB?**

A: Yup. But it's a good name so we're repurposing it.

**Q: What about Android?**

A: TouchDB for Android is stable enough to be used by some apps already, but it does not yet have the latest features for integration with Couchbase Mobile. We are working on it.

**Q: Will Couchbase Mobile work with Apache CouchDB servers?**

A: No. The Sync Gateway server has custom functionality for access control and data routing that isn't available in Apache CouchDB.

**Q: What about my existing mobile app that uses Couchbase Lite to sync with Apache CouchDB?**

A: No problem! Couchbase Lite's sync protocol will remain compatible with Apache CouchDB's, so your app will continue to work. If you later need the full capabilities of Couchbase Mobile, you can make minor changes to the mobile app to switch to it.
