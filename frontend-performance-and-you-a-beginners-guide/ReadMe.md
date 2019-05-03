# Frontend Performance and You: A Beginner's Guide by Daniel Cousineau

## Always measure first

* Google analytics
* Metrics
    * Parse & Compile
    * Document Interactive
    * Document Content Loaded
    * (Time To Interactive)
* WebPageTest.org
    * Third party scripts will kill your score
* https://speedcurve.com
* Google Lighthouse

## Making your servers faster is another talk...

## Minify your outputs

* Uglify is now terser
* cssnano
* CDN's -- not just for images
* Compress content over the wire

## Reduce request count

* Domain sharding is old and busted
* Inline initial data into HTML payloads

## Preload / Prefetch

* Put script tags at the bottom of your html body.
* `<link rel="preload" href="app.js" as="script" />`
* preload - use very soon
* prefetch - will probably use this soon
* What about h2 push?
    * cache issue
    * proxy support
* Load only what you need
    * code splitting comes for free with webpack
    * load only visible images
    * Loading & rendering offscreen images can impact real performance
    * Better images - srcset in img element
    * Smarter image formats (never send png's)`
* Don't always show loading indicator. Depending on how much time it will actually take

## Additional Reading

* Repaint, reflow
* Chrome DevTool Audits
* Go to Josh Holme's talk tomorrow
* Service Workers & offline-plugin for webpack

    
    