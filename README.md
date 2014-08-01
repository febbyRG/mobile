Couchbase Mobile 
======

The modern app experience is decent, but it could always be better, more present, and more responsive. We want developers to be prepared for the next generation of apps that demand to be always-present and always-responsive, but without the expensive development and deployment costs usually associated with solutions, such as SAP Anywhere.

We also want our developers to have options, flexibility, and the ability to grow. As a NoSQL leader, we looked to build a robust platform that mobile developers can easily understand and build on top of. 

We're excited to introduce [**Couchbase Mobile**](http://www.couchbase.com/mobile), a suite of products that make remote app and syncing experiences easy. Couchbase Mobile introduces two major new products that you can find here in accompaniment with our main product, Couchbase Server. They are as follows:

* **Couchbase Lite** - On-device, lightweight, native, embedded JSON database. We support Objective-C, Android Java, Java and .NET.
* **Couchbase Sync Gateway** - A scalable secure sync tier.
* **Couchbase Server** - A high-performance, scalable, JSON database that's been battle-tested in heavy-traffic mission critical deployments serving millions of users.

Visit our [mobile developer portal](http://developer.couchbase.com/mobile/) for the latest downloads and documentation of Couchbase Sync Gateway and Couchbase Lite, and learn more about Couchbase Server [here](http://www.couchbase.com/couchbase-server/overview)

Or, step right into our code! You will find our main project repos above.

## Use Cases

We've been working with community users and customers on use cases like:

* **Medical records** - this data is a great fit for schemaless JSON storage. It's also critical that it be available wherever the health care provider goes, regardless of network conditions.
* **Customer loyalty and Point-of-Sale** - we see a lot of these apps already using our sync technology, and we've been working with some developers closely to ensure a smooth ride.
* **Airline in-flight customer support** - pilots and flight attendants benefit from having easy access to data about passengers and flight plans, with the ability to dynamically refresh the data when they are on the ground.
* **Delivery vehicle fleet management** - tracking vehicle telemetry and routing it to the cloud when connections are available is a great fit for Couchbase Mobile
* **Social media platforms** - chat and game companies often take a portfolio approach. By offloading the details of pushing data across mobile networks, they can focus on rolling out compelling content that utilizes a common backbone.

##Cross-platform tool support
In addition to client-side native support for iOS, Android, Java and .NET, we also are integrated with some of the most popular mobile platforms today.

### PhoneGap / Cordova

HTML5 developers can build rich hybrid apps backed by our Couchbase Mobile stack, with our support for the PhoneGap/Cordova platform. 

You can check out the [Cordova component](http://plugins.cordova.io/#/package/com.couchbase.lite.phonegap), or visit the GitHub repo right [here](https://github.com/couchbaselabs/Couchbase-Lite-PhoneGap-Plugin).

For an example app, visit our PhoneGap tutorial to get started off of our Developer Portal, [here](http://developer.couchbase.com/mobile/get-started/get-started-mobile/phonegap/index.html).

### Xamarin

Similarly, we provide support to .NET developers looking to do cross-platform development for iOS and Android with Xamarin. This project sources from our on-going .NET client development to bring a rich and broad set of supports for .NET developers.

You can learn more from our [Xamarin component page](http://components.xamarin.com/view/couchbase-lite-net/), or visit our GitHub repo right [here](https://github.com/couchbaselabs/couchbase-lite-net/).

## Roadmap

We're continuing to develop support for a variety of languages and platforms for our Couchbase Lite client, with plans to buid Javascript and Unity support in the works.

But, we have plenty of room to grow in feature work on both the local client, and at the sync tier. We also are continuing to push the boundaries for performance and scaling with our products.

A sneak peek into some of the work we are looking to roll-out next include:

* Security features, including local encryption
* Raising the limit for Attachment sizes
* More granular replication options, such as channel subsets based on time, geography, and more
* Pushing map/reduce requests from client to server
* Developer and admin tooling
* Better support for P2P use cases

##Community

We are an open source team and as always, we are actively seeking feedback. We use GitHub extensively to build and collaborate, so do feel free to contribute by sending us issues, pull requests, and feature requests/enhancements! In addition, [join our mailing list](https://groups.google.com/forum/#!forum/mobile-couchbase) to discuss your use case, suggest improvements or get help with your applications.


## FAQ

**Q: Is this the same thing as Syncpoint?**

A: No; Syncpoint was an earlier prototype that had similar goals but a different architecture. Couchbase Mobile takes advantage of Couchbase Server for scalability and provides a simpler model for developers.

**Q: Will Couchbase Lite work with Apache CouchDB servers?**

A: No. The Sync Gateway server has custom functionality for access control and data routing that isn't available in Apache CouchDB.

**Q: What about my existing mobile app that uses Couchbase Lite to sync with Apache CouchDB?**

A: No problem! Couchbase Lite's sync protocol will remain compatible with Apache CouchDB's, so your app will continue to work. If you later need the full capabilities of Couchbase Mobile, you can make minor changes to the mobile app to switch to it.
