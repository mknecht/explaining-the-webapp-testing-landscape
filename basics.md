# The Basic Ideas

All the hype boils down to this simple architecture:

    [Tester] <-> [Client] <-> [Web Application]

Any test setup you can do requires these three things:

  * The **web application** that is being tested. For example, http://www.github.com
  * Your **tester** that runs test scenarios against the webapp and verifies assumptions about them.
    * For example, you could write a test against GitHub to make sure that opening a new issue in your project works.
    * A test might be written in Python or JavaScript or Ruby.
  * A **client** that accesses the web application, performing the steps of your testing scenario. In one form or another, the client includes a browser, like Firefox or Chrome.

The technologies I mentioned above are either connecting your test code with the client or are the client itself.

Now, there's two different ways to setup your browser.

  1. Your browser runs only local, and
  2. The whole setup is built so that the browser can run remotely.
     This is what Selenium's WebDriver is supporting.

So, let's zoom in for greater detail. We start with the simple case:

## Controlling a Local Browser

that the
browser runs on the same machine as the

    [       Tester      ]     [         Client         ]

    [Test] <-> [Controller API Client] <-> [Controller] <-> [Browser]

  * Your test code uses a library to drive the browser. Let's call it a []()
  *


Typical Examples:

  * Webtest + HtmlUnit
  * Selenium library + Browser without Selenium Server **???**

## A Browser Remote

    [            Test             ]               [        Client          ]

                                    <Remote API>
    [Testcode] <-> [Client library]     <->       [Controller] <-> [Browser]
