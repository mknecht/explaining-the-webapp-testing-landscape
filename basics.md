# The Basic Ideas

All the hype boils down to this simple architecture:

    [Test] <-> [Client] <-> [Web Application]

Any test setup you can do requires these three things:

  * The **web application** that is being tested. For example, http://www.github.com
  * Your **test** that runs test scenarios against the webapp and verifies assumptions about them.
    * For example, you could write a test against GitHub to make sure that opening a new issue in your project works.
    * A test might be written in Python or JavaScript or Ruby.
  * A **client** that accesses the web application, performing the steps of your testing scenario. In one form or another, the client includes a browser, like Firefox or Chrome.

The technologies from the word cloud are either connecting your test code with the client or are the client itself.

So, let's zoom in for greater detail.

## Zooming In: API and Orchestration

How does your test talk to the browser? How do you get your
“I want to click on the ‘Buy’ button.” to the browser?
That's the **API**'s role; it's giving your test the ability to
control the client.

What actually makes Firefox click on a button, if it's not your touchpad?
That's the /Browser Controller/, or /Controller/ for short.

So, how does that look now?

    [Test] <-----------> [         Client         ]

    [Test] <-> [API] <-> [Controller] <-> [Browser]

With that, we can already discuss a few common scenarios:

  * Webtest + HtmlUnit
  * Selenium library + Browser without Selenium Server **???**

## A Browser Remote

    [            Test             ]               [        Client          ]

                                    <Remote API>
    [Testcode] <-> [Client library]     <->       [Controller] <-> [Browser]
