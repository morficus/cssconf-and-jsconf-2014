# Making Your CSS Happy aka: testing your CSS
by [Christopher Burgmer](http://cburgmer.wordpress.com/)

Every layer of development has some type of testing methodology, but that is not the case whe nit comes to HTML+CSS.
Testing tools provide a "safety net" for when making changes...but we don't have this for the HTML+CSS, so makign changes to either old or large applciations comes very risky.  

Some tools take screenshot and indicate when something changes - not if it's broken, that it has changed. Then the developer just needs to check the changes and see if they were expected / planned changes or not. 

There are others that do similar stuff:
* Wraith: https://github.com/BBC-News/wraith
* PhantomCSS: https://github.com/Huddle/PhantomCSS
* Hardy: https://github.com/thingsinjars/Hardy
* CSScritic: https://github.com/cburgmer/csscritic
* Many others here: http://csste.st/

By using theese tools, you learn a lot about your UI compoennts and how they change over time.  
A lot of them take a screenshot of your item and them comparethem.  But screenshots can be flaky: content changes and rendings are unique snowfles (different for every browser), so you might need to use a different solution for different ploblems - find out what works for you!  

Mixing concepts from talk #1 (styleguide driven development) - one neat trick would be to run your CSS tests against your styleguide (create tests for individual modules) in place of your app.  

Downside is that at the moment there is no way to automate these tests (aka: run on every commit or from a CI), so some manual inspection is still necesary. Tho tools like PhantomCSS allow you to run these tests from the CLI.
