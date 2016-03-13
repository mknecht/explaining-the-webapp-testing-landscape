# The Client

Firefox or Internet Explorer are typical examples of a client:

* It requests a page of your app and renders it.
* It allows you to interact with the page by clicking buttons, selecting check boxes and so on.
* It sends inputs, such as form contents or cookies to your web app.
* It runs JavaScript of your webapp and other plugins that the page uses, changing the page while doing so.
* It navigates the web app by following links, or visiting new URLs.

The client doesn't have to be a browser as you know it from your Desktop environment. At the end, it's the thing that interacts with your web application by requesting pages and sending input back to your test.

Clients come in three flavors:

* **GUI Browsers**
* **Headless Browsers**
* **Browser Simulators**

We'll look at those below.

Each browser is based on a **browser engine**:
The engine can read and render HTML, knows about CSS,
can probably run JavaScript and (directly or thru plugins)
implements a lot of other webstandards.

Examples for browser engines are:

* [Gecko](https://developer.mozilla.org/en-US/docs/Mozilla/Gecko) is the browser engine behind Mozilla's **Firefox**. ([Wikipedia](https://en.wikipedia.org/wiki/Gecko_%28software%29))
* [Servo](https://github.com/servo/servo) is the next-generation engine from Mozilla.
* [WebKit](http://www.webkit.org/) originally powered **Safari**, but then was forked and is now at the heart of Google's **Chrome** and **Opera**.

In a finished browser, the browser engine comes with a **JavaScript engine**, the thing that reads and runs JavaScript code.
Examples for JavaScript engines are:

* [Rhino](https://developer.mozilla.org/en-US/docs/Mozilla/Projects/Rhino) is developed by Mozilla and written purely in Java. ([GitHub](https://github.com/mozilla/rhino)) It was built to be run standalone, provides a shell, and is therefore suited for prototyping JS and testing your UI components.
  * [Nashorn]() is it's predecessor. ([Wikipedia on Nashorn](https://en.wikipedia.org/wiki/Nashorn_(JavaScript_engine)))
* [SpiderMonkey]()    ([Wikipedia](https://en.wikipedia.org/wiki/SpiderMonkey_(JavaScript_engine)))
* V8 is built by Google and powers Chrome    ([Wikipedia](https://en.wikipedia.org/wiki/SpiderMonkey_(JavaScript_engine)))
*

Let's get an overview of the different types of clients. I'll point out the big differentiators.

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
  * **They're heavy.** They need lots of CPU and memory. This ties in with speed, but is remarkable by itself: If you want to run many browsers in parallel, resource consumption becomes a problem.

## Headless Browsers

Headless browsers are using the browser engine of one of the GUI browsers
above, but are not actually showing the page.
(The *missing head* is the graphical user interface, the thing you see.)
In other words, these browsers you start for example in the consoule,
and then you need to use an API to navigate, click, scroll and select.

  * [PhantomJS](http://phantomjs.org/) uses WebKit, and is the de-facto standard to run your UI tests headlessly. With [GhostDriver](#ghostdriver) included
  * [SlimerJS](http://slimerjs.org/) uses Gecko and is a comparatively new addition.

Why would you use a headless browser?

  * **Much faster** than a GUI browser,
    while still being a **real browser engine**.

Why wouldn't you?

  * Not **what your customers use**: They use the same engine as a GUI browser, but are not the same program that your customers use.
  * Very **limited choice in terms of browser engine (version)**. AFAIK there is no headless IE, and if you want to test a specific version of Webkit odds are PhantomJS does not offer that one.
  * **Debugging is harder** without a UI. Sure, you can save screenshots, but sometimes *seeing* the test run is so much easier.
    * Note that for example on [Browserstack](#browserstack) you can watch a *video* of the test run.

### Cutting off the head (of a GUI Browser)

There are ways to get the advantage of using a real browser, while avoiding the window being on your desktop, mess with your mind and mouse.

http://stackoverflow.com/questions/17062453/selenium-running-headless-firefox-browser-in-windows

https://en.wikipedia.org/wiki/Xvfb
https://azevedorafaela.wordpress.com/2014/10/30/running-selenium-headless-firefox-in-ubuntu/
http://tobyho.com/2015/01/09/headless-browser-testing-xvfb/
http://www.jpalomaki.fi/?p=403



## Browser Simulators

* HtmlUnit
* WebTest Canoo
* Zombie http://zombie.js.org/#browser
