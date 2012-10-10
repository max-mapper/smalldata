Common web stacks have a database and custom API middleware code that either provide paginated access to data through XML/JSON or RSS feeds or bulk downloads via CSV. The problem with this approach is that there is no standard way of keeping subscribers in sync.

**Some solutions:**

* use [[http://code.google.com/p/pubsubhubbub/]], which uses a third party hub to keep the one publisher and N subscribers in sync
* use CouchDB style replication, which uses a peer to peer replication scheme to keep two endpoints in sync with each other

### CouchDB <==> MongoDB [[replication]]
Mongo has an "oplog", but it's size is set by the user and therefore doesn't store the entire history of every change like Couch does. An approach to replicating using the oplog might be:

* the initial mongo => couch replication you simply copy all documents from mongo into couch
* upon subsequent [[replication]] requests you can convert the oplog into a couch _changes feed and checkpoints. if you need stuff going back further than the oplog stores then you simply brute force replication as in the initial replication

Mongo code that might be useful: https://github.com/mikejs/photovoltaic/blob/master/pv.py#L65

**Commonly Asked Questions:**

Q: How does peer to peer replication of CouchDB address the issue of permissions user authenticated data?

A: encryption isnt in the scope of the replication protocol, so you would have to publish an encrypted feed of data that only people who have the key can decrypt.

Q: What is the key difference between "small" and "big" data?

A: the usage of data in respect to who created and who owns data. NYTimes summed it up well in [this article](http://www.nytimes.com/2011/04/24/business/24view.html?_r=1&ref=technology)