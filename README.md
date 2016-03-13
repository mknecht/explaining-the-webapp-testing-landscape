# The Confusion

In the technology landscape of **testing web applications end-to-end** there are a lot of technologies floating around:

    Selenium Server, PhantomJS, Web- and GhostDriver, CasperJS, WebKit

For a first-timer, this name soup looks rather messy, and is definitely hard to understand.
(And not without reason: I find a lot of concepts are being used rather vaguely
or ambiguously.)

Here, I'll answer these questions:

1. What is it?
1. Where can it be found in the technology landscape?

## What I don't care about.

By the way, here I'm interested in *end-to-end tests* only. This means tests that interact with your web application running as if in production. No mocking the database, no unit-testing JavaScript UI components. The whole thing. (I'll mention some technologies, like Rhino, but only to point out where the scope of end-to-end testing ends.)

# Let's get started!

First, you really should [dig the basics](basics.md).
It's a short read, but gives us the words and concepts we need.

With this knowledge, we can explore common use cases:

* [Running Selenium tests with a local PhantomJS]
* [A Selenium Grid Setup] to parallelize tests.
* Running your tests against [multiple browsers with Browserstack]

We can dig into the muddy details: [Clients](clients.md) .
And there is a dedicated page on [Selenium](selenium.md) cuz that's a name cloud if I've ever seen any.

Or, if you want to look up a technology, you can head over to the [Glossary](glossary.md).


# Contributing

Found an error? A gross omission? A fatal misconception?

This is great!

Please open an issue or just fix it with a PR.


# Can I share or reuse this? (License)

Please do. Together we learn more.

The text (*.md and *.svg) is licensed under CC0 (see LICENSE-ARTICLES). The source code (*.html and *.js) is licensed under MIT (see LICENSE-CODE).

I'd appreciate (but don't require) a [reference to the GitHub repository](https://github.com/mknecht/explaining-the-webapp-testing-landscape).

# Left to do


Remote Control APIs

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


* Architecture
https://github.com/ariya/phantomjs/wiki/Architecture

* unsorted

https://saucelabs.com/features#features-cross-browser
https://experitest.com/
Selenium RC
http://sahipro.com/
Canoo Webdriver
