# The Confusion

In the universe of testing web applications end-to-end there are a lot of technologies floating around: Selenium Server, PhantomJS, Web- and GhostDriver, CasperJS, and many more. For a first-timer, this name soup looks rather messy.
(And not without reason: I find a lot of concepts are being used rather vaguely
or ambiguously.)

Here, I'll answer these questions: *What is it?* And: *What's its place in the universe of testing web apps?*

By the way, I'm interested in end-to-end tests, meaning tests that interact with your web application running as if in production. No mocking the database, no unit-testing JavaScript UI components. The whole thing. (I'll mention some technologies, like Rhino, but only to point out where the scope of end-to-end testing ends.)

# The Very Basics

All the hype boils down to this simple architecture:

    [Test] <-> [Client] <-> [Web Application]

Any test setup you can do, requires these three things:

* The **web application** that is being tested. For example, http://www.github.com
* Your **test** that runs scenarios and verifies assumptions about these.
  * For example, you could write a test for GitHub to make sure that assigning your project a star works.
  * A test might be written in Python or JavaScript or Ruby, using libraries such as Splinter or CasparJS or Watir.
* A **client** that accesses the web application, performing the scenario steps and gathering needed data. The client can be a browser, like Firefox or Chrome, but does not need to be.

The technologies I mentioned above are either connecting your test with the client or are the client itself.

Let's start with the client:

# The Client

A browser, like Firefox, is a typical client:

* It requests a page of your app and renders it.
* It allows you to interact with the page by clicking buttons, selecting check boxes and so on.
* It sends inputs, such as form contents or cookies to your web app.
* It runs JavaScript of your webapp and other plugins that the page uses, changing the page while doing so.
* It navigates the web app by following links, or visiting new URLs.

The client doesn't have to be a browser as you know it from your Desktop environment. At the end, it's the thing that interacts with your web application by requesting pages and sending input back.

Clients come in three flavors:

* **GUI Browsers**
* **Headless Browsers**
* **Browser Simulators**: Browsers are the things you know: Chrome, Firefox, Safari

## GUI Browsers

These you know, I'll simply list a few: Chrome, Firefox,

## Headless Browsers

  * phantomjs
  * slimejs


## Browser Simulators

  * WebTest Canoo


# Driving the Client

One important question remains:

    How do you control the browser?



APIs / Drivers

* Webdriver
* Splinter http://splinter.readthedocs.org/en/latest/
* WebTest https://pypi.python.org/pypi/WebTest
* Watir http://watir.com/

Remote Controllers

* CasperJS http://casperjs.org/

Browser Controllers

* Selenium Server
* Selenium Grid

Tools

* Selenium IDE

Browsers


Browser Engines

* Webkit
* Gecko
* Servo https://github.com/servo/servo

JS Engines

* Rhino https://developer.mozilla.org/en-US/docs/Mozilla/Projects/Rhino
* V8



links:
http://slides.com/justinklemm/phantomjs-casperjs-other-automated-testing-tools/#/
https://tommorris.org/posts/8109
http://splinter.readthedocs.org/en/latest/#drivers
https://pypi.python.org/pypi/zope.testbrowser/#detailed-documentation
