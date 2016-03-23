# Explaining the Webapp Testing Landscape

## WIP

**BEWARE: this is work in progress, and far from done (2016-03-23)**

## The Confusion

In the technology landscape of **testing web applications end-to-end** there are a lot of technologies floating around:

    Selenium Server, PhantomJS, Web- and GhostDriver, CasperJS, WebKit

For a first-timer, this name soup looks rather messy, and is definitely hard to understand.
(And not without reason: I find a lot of concepts are being used rather vaguely
or ambiguously.)

For all of those, I'll answer these questions:

1. What is it good for?
1. Where does it fit in the tech landscape?

### What I don't care about.

I'm interested in *end-to-end tests* only. This means tests that interact with your web application running as if in production. No mocking the database, no unit-testing JavaScript UI components. The whole thing. (I'll mention some technologies, like Rhino, but only to point out where the scope of end-to-end testing ends.)

## Let's get started!

First, you really should [dig the basics](basics.md).
It's a short read, but gives us the words and concepts we need.

With this knowledge, we can explore common use cases:

  * [Webtest-based Test suites](#wip)
  * [Running Selenium tests with a local PhantomJS](#wip)
  * [A Selenium Grid Setup](#wip) to parallelize tests.
  * Running your tests against [multiple browsers with Browserstack](#wip)

We can dig into the muddy details: [Client API Providers](#wip), [Orchestrators](#wip) and [Browsers with their Controllers](clients.md).

Selenium is a tech cloud if I've ever seen any, so there is a [dedicated page on Selenium](#wip).

Or, if you want to look up a technology, you can head over to the [Glossary](glossary.md).


# Contributing

Found an error? A gross omission? A fatal misconception?

That's great!

Please open an issue or just fix it with a PR.


# Can I share or reuse this? (License)

Please do. Together we learn more.

The text (*.md and *.svg) is licensed under CC0 (see LICENSE-ARTICLES). The source code (*.html and *.js) is licensed under MIT (see LICENSE-CODE).

I'd appreciate (but don't require) a [reference to the GitHub repository](https://github.com/mknecht/explaining-the-webapp-testing-landscape).
