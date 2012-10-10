### web based data QA
An open source simplified version of this would be nice: [[http://wiki.freebase.com/wiki/Refinery]]. We could do it with CouchDB + Google Refine: [[https://github.com/maxogden/refine-uploader]] & [[https://github.com/maxogden/removalist]]. [[http://fluidinfo.com/cookbook/]] is reminiscent of this idea as well

further reading on this topic: [[http://blog.okfn.org/2011/03/31/building-the-open-data-ecosystem/]]

### open civic data
there is an initiative to standardize civic data [here](https://github.com/opencivicdata). making openstreetmap data more easily replicable would also be [nice](http://twitter.com/#!/vmische/status/62796977036984320)

### p2p wikipedia CDN
let anyone be part of the wikipedia data center. an html5 layer on top of wikipedia would intelligently prefetch articles from a p2p hosted CDN


    22:02 < maxogden> basically we would make a big p2p CDN for wikipedia 
    22:02 < maxogden> where anyone could sign up seti@home style and run a process on their server
    22:02 < maxogden> and they would get assigned a chunk of wikipedia to host
    22:03 < maxogden> and then people browsing wikipedia would run special javascript
    22:03 < maxogden> so if you are on the page for San Francisco
    22:03 < maxogden> it would pre-fetch all the linked page content from the p2p cdn by doing CORS requests to a reverse proxy that can query the CDN over 
                      telehash
    22:03 < maxogden> :D
    22:03 < maxogden> so that way when you click on links
    22:04 < maxogden> they are already loaded in your browser so the page load is instantaneous
    22:04 < maxogden> and it doesnt have to hit wikipedias data center
    22:04 < maxogden> it would only work on reads and not edits of course
    22:04 < maxogden> and also uniquely fits wikipedia because it doesnt really matter if the content you get is a few minutes out of date

## Data ownership and sharing
### Refuge
From [github page](https://github.com/refuge/refuge):
> Refuge main goal is to design an opensource, free, decentralized and secured and eventually anonymous platform. This platform will allow to share, render information and exchange messages offline or online. Information is on each nodes.

### Locker Project
From [home page](http://lockerproject.org/):
> Locker gives people ownership over their personal data and clear control over how it's protected and shared. Providing flexible APIs for access to that data, Lockers are a powerful way for developers to build applications that leverage rich personal data.