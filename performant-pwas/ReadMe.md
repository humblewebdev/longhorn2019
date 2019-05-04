# Performant PWAs

> Josh Holmes

*Update:*

- MS Edge team moving to Chromium in the coming months
- Edge will be ported to MacOS also, and if customers want it, Linux
- Have already made 350 PRs to Chromium in Canary
- [Release URL](https://github.com/MicrosoftEdge/MSEdge)

## Progressive Web Apps (PWA)

- It's essentially a website that can work as an installable app.
- Browser extensions still run in a PWA.

### Requires

- HTTPS
- manifest.json      - Example is https://m.twitter.com/manifest.json
- service-worker.js  

[pwabuilder.com](https://pwabuilder.com)

## Uses of a service worker

- Local caching of assets and cache flushing
- Push notifications

## Using a service worker

- On page load, you must register a service worker.
- Afterwards, all changes to your service worker are handled by the browser itself.

```js
navigator.serviceWorker.register('service-worker.js', {
    scope: './'
}).then(function (reg) {
    // do something
});
```

## Performance Tuning

- Just like performance tuning a website.
- What is your context? Meaning, what is the most important thing for your users? Most users prefer a site be easy to navigat first, be fast, and only then be reliable. Most users don't care at all about personalized content.
- A 1 second delay can reduce 7% conversions.
- 53% of people abandon a website that takes more than 3 seconds to load.
- Gave an in-depth overview of the DOM painting lifecycle.

## Steps for better performance

- Move JS files to the bottom of the document
- Use native features when possible (e.g. `required` attribute instead of JS form validation)
- Only use assets as needed
- Optimize everything
- Think about how and when you load assets (lazy-loading preferable)
- Use semantic HTML (e.g. `<header>` vs `<div class="header">`). It's actually faster to render too.
- Use `aria` for most form fields.
    - Useful attribute for form fields `autocorrect="off"` and `autocapitalize="off"`
- Use CSS grid. Far easier on the browser than floats and older ways of doing stuff.

## Only using networks when you need them

- Libraries / frameworks are probably on a CDN. You should default to CDNs whenever possible.
- `rel="prefetch"` grabs the file without parsing it and immediately goes to cache.
- `as="script"` grabs the file, parses it, but does not immediately effect the DOM. Is also cached.
- Check out **10k Apart**. Yearly competition to build awesome websites with 10k or less.

## Optimize Everything

- Compile/minimize CSS to remove spaces, variables, and purge any unused stuff.
- Compress with GZip, Brotli, and any other shrinkers
- Same things for JS. Only additional concern really is the order of execution.

## Think about When you want to load assets

- Anything that is not required up front shouldn't be loaded up front.
- Add `defer` attribute to things that are not needed immediately.
- Add `async` attribute to things that we just want to run whenever it's possible.
    - Should not rely on other `async` JS files. Should all be stand alone or race-conditions are possible.
- If you can use a server with HTTP2, that is by far the best, so that lots of files can be pushed at once.

## How you load assets

- CSS file `media="only screen"` means only clients that have a screen load the file.
- Conditional imagery, based on CSS media queries
- Conditional animations
- Evaluate images on a case-by-case basis. Especially for mobile. Does it block actual content? "Not every article needs a picture"
- Provide WebP format images for browsers than can support it (Chromium based browsers)
- If possible, set backgrounds of images to a solid color, so a compression library can blur it easily and save lots of data.