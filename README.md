# The Confusion

In the universe of testing web applications end-to-end there are a lot of technologies floating around:

    Selenium Server, PhantomJS, Web- and GhostDriver, CasperJS, WebKit

For a first-timer, this name soup looks rather messy, and is definitely hard to understand.
(And not without reason: I find a lot of concepts are being used rather vaguely
or ambiguously.)

Here, I'll answer these questions:

    *What is it?*

And:

    *What's its place in the universe of testing web apps?*

By the way, I'm interested in *end-to-end tests*, meaning tests that interact with your web application running as if in production. No mocking the database, no unit-testing JavaScript UI components. The whole thing. (I'll mention some technologies, like Rhino, but only to point out where the scope of end-to-end testing ends.)

# The Very Basics

All the hype boils down to this simple architecture:

    [Test] <-> [Client] <-> [Web Application]

Any test setup you can do, requires these three things:

* The **web application** that is being tested. For example, http://www.github.com
* Your **test** that runs scenarios against the webapp and verifies assumptions about them.
  * For example, you could write a test against GitHub to make sure that opening a new issue in your project works.
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
* **Browser Simulators**

Each browser is based on a *browser engine*:
Something that can read and render HTML.
Examples for browser engines are:

* Gecko
* [Servo](https://github.com/servo/servo)
* WebKit

In a finished browser, the browser engine comes with a *JavaScript engine*, the thing that reads and runs JavaScript code.
Examples for JavaScript engines are:

* [Rhino](https://developer.mozilla.org/en-US/docs/Mozilla/Projects/Rhino) is written purely in Java.
  * It was built to be run standalone, and is therefore suited to unit-test your UI components.
* V8

## GUI Browsers

These clients you know. I'll simply list a few, together with the browser and JavaScript engine that they're based on:

  * Chrome
  * Firefox
  * Internet Explorer
  * Opera
  * Safari

Why would you choose GUI browsers?

  * **They're the real thing**: If your test succeeds on Chrome, you know the tested scenario works in a real browser; the same as your users are running.

Why wouldn't you?

  * **They're slow as.** If you're going for more than a Smoke Test, you'll find yourself waiting a lot. Speeding up end-to-end tests is an artform in itself.
  * **They might use your mouse.** If you're using the real thing, it means a window will pop up, unceremoniously steal your mouse cursor and text caret and start clicking and typing. You won't be able to work. (Yay! Maybe it's a plus?) Oh, and for a whole while, see above. (That can be worked around, [see below](#headless-gui-browsers).)
  * **They're heavy.** They need lots of CPU and memory. This ties in with speed, but is remarkable by itself: If you want to run many tests in parallel, resource consumption becomes a problem.

## Headless Browsers

Headless browsers are based on the browser engine of one of the GUI browsers
above, but are not actually showing the page.

The missing head is the graphical user interface:

  * phantomjs
  * slimejs

### Headless GUI Browsers

http://stackoverflow.com/questions/17062453/selenium-running-headless-firefox-browser-in-windows

https://en.wikipedia.org/wiki/Xvfb
https://azevedorafaela.wordpress.com/2014/10/30/running-selenium-headless-firefox-in-ubuntu/
http://tobyho.com/2015/01/09/headless-browser-testing-xvfb/
http://www.jpalomaki.fi/?p=403



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

links:
http://slides.com/justinklemm/phantomjs-casperjs-other-automated-testing-tools/#/
https://tommorris.org/posts/8109
http://splinter.readthedocs.org/en/latest/#drivers
https://pypi.python.org/pypi/zope.testbrowser/#detailed-documentation
