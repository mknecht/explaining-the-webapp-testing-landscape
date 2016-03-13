# The Very Basics

All the hype boils down to this simple architecture:

    [Test] <-> [Client] <-> [Web Application]

Any test setup you can do requires these three things:

  * The **web application** that is being tested. For example, http://www.github.com
  * Your **test** that runs scenarios against the webapp and verifies assumptions about them.
    * For example, you could write a test against GitHub to make sure that opening a new issue in your project works.
    * A test might be written in Python or JavaScript or Ruby, using libraries such as Splinter or CasparJS or Watir.
  * A **client** that accesses the web application, performing the steps of your testing scenario. In one form or another, the client includes a browser, like Firefox or Chrome.

The technologies I mentioned above are either connecting your test with the client or are the client itself.

So, let's zoom in for greater detail:

               [        Client          ]

    [Test] <-> [Controller] <-> [Browser]

  * Your test uses a library to drive the browser. I call it a [](
