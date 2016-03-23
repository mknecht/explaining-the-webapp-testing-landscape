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

## Zooming In: API, Controllers and Launchers

Let's say in your test you want to make Firefox click the “Buy” button on your web app's landing page.

How do you put that in your test? And how do you get that command
“Press the ‘Buy’ button!” to Firefox?
That's the **API**'s role; it's giving your test the ability to
control the browser.

Usually, the API layer consists of a library in Your-Language-Of-Choice, for example [selenium](https://pypi.python.org/pypi/selenium/) in the case of Python. That library is the part that you use directly.
`selenium` then talks to the controller over some sort of API, too, usually using a network protocol, like the WebDriver wire protocol.

When you've got your command over, what actually makes Firefox click the button, if it's not your touchpad doing it?
That's the **Browser Controller**, or *Controller* for short. In Firefox case, that'd usually be [Marionette](glossary.md#marionette).

So, how does our architecture look now?

    [Test] <-----------> [         Client         ]

    [Test] <-> [API] <-> [Controller] <-> [Browser]

With the technologies I used as examples:


                                     Webdriver
    [Test in Python] <-> [selenium] <---------> [Marionette] <-> [Firefox]

Uh, but who's actually *starting* your Firefox? Surely, you're not doing that manually every time you run your tests? Right, you need a **Launcher**: Something that makes sure the browser you need is up and running. In our case, `selenium` library is also the Launcher.

That's not a given: Think about a browser on another computer, like you're running your tests on a Windows machine, but want your tests to use Safari on MacOS. Then, the Launcher can't really be on your Windows machine, but needs to be *on the MacOS*. [Selenium Server](glossary.md#selenium-server) is an example for a launcher that's useful for that scenario.

With all this, we can already deeply understand a few common scenarios:

  * [Webtest-based Test suites](README.md#wip)
  * [Running Selenium tests with a local PhantomJS](README.md#wip)

## Adding Features: Prettier tests and more browsers

DSLs, abstraction libraries and orchestrators
