# CSS and the critical path
by [Patrick Hamann](http://twitter.com/patrickhamann)

slides: [https://speakerdeck.com/patrickhamann/css-and-the-critical-path-cssconf-may-2014](https://speakerdeck.com/patrickhamann/css-and-the-critical-path-cssconf-may-2014)
src code for The Guardians mobile site, and their optimizations: [https://github.com/guardian/frontend](https://github.com/guardian/frontend)  

As web developers, we should no longer think in seconds. It should be milliseconds. 
Users perception of an application really changes if things take a certain amount to load
* 0.1s = user experience slgiht delay, but feels alsmost instant
* 1.0s = user persives the machine "is working"  
* 10.0s = task is abandonded  

So we want to target 1.0s for ALL our page loads.    
But network latency (on mobile) takes ~600ms, so we really only have ~400ms to do our thing...  
This means we need to get CSS down from the network ASAP (even before the JS files) since it will be the first thing the user sees, even before trying to interact with the page.  

(We define "critical path" as the main thing that the user is here for (in the case of this talk, the new article))  

Techniques implemented by The Guardian to speed up their critical path:  
1. To ensure that our criticla path CSS gets to the user FAST... we put some in-line CSS (at the top of the page) so that the browser gets all the paint and layout info in a single request. The percived benefits are huge.  
2. Another useful technique is to store the non-critical path CSS in localStorage so the broswer doesn't have to fetch it the 2nd time around.  

This system also creates more resilient systems. We only need 1 request to get ALL the information necesary for painting and layout.

Resoureces! [http://speedcurve.com/](http://speedcurve.com/)  

In place of doing the in-lining manually or with a build tool... you can use the Apache (or nginx) "pagespeed" module to do this at a "proxy-level". There are some risks with doing this, but it is still an option.  

HTTP/2 and ServiceWorker will avoid the need for all these "hacks" when they are finalized.
