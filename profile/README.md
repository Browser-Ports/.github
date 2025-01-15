# Browser Ports

Browser Ports is an organization dedicated to advancing browser technology and porting it to the web. We dream of a reality where you can have an entire OS on the web and a browser and apps that work well and are sandboxed.

Most of these projects are a long way off from becoming reality.

## How you can talk to us

[![](https://dcbadge.limes.pink/api/server/2uuGF9b3DH)](https://discord.gg/2uuGF9b3DH)

Alternatively, use the bridges:

- [Revolt](https://rvlt.gg/QDZeFFZf)
- (Matrix coming soon!)

## Words from the founder

Hello, my name is Ryan. For the past five years, I've been learning programming and immersing myself in web dev, with Browser Ports being the final destination in mind. I've started making web proxy and sandboxing technology such as aero/AeroSandbox in hopes of developing it to be enough for a browser port. I've been watching the web evolve, and I've seen a lot of new uses for my tech. For example, combating Google's reckless behavior of removing MV2 features and being a hindrance to adblockers. Over the years, Firefox has become more and more like a web app, making it easier to maintain with a smaller team, which also has the side-effect of making it perfect for Browser Ports. To contrast this, Chromium, in many areas, hardcodes the UI in C++ and Views/Skia. They have been making a reasonable effort with the advancement of WebUI, especially since the 2023 refresh. 

I am committed to these projects because nobody has made the connection that the same web proxies previously used for unblocking have so much standalone potential. Any idea I explore with Browser Ports leads to many new ideas I never thought of before. I only work on projects for things that have never been made or thought about. This is the most unique sea of projects I can work on.

I was planning on making web OS software that lets you use real desktop apps similar to ChromeOS with cloud syncing as an environment you can take anywhere. [Anura](https://github.com/MercuryWorkshop/anuraOS) fills this gap now, except for the cloud syncing abilities; however, [Puter](https://github.com/HeyPuter/puter) is filling that gap so that I will work on support for their web os on my projects, too (however, not upstream, most likely). I'm working with Anura/MW to port my projects from Browser Ports there. They have a dev team and everything ChromeOS has except for enterprise device/browser policies (which I plan to implement). Android app support is increasingly more relevant because Chrome OS is becoming more like Android.

## What the future for Browser Ports tech, really (why invest so much time into this)

Browser Ports will also have another significant impact in that the same tech can be repurposed to the benefit of many

- I genuinely believe that Browser Ports can make remote browsers (names like [Maxthon Cloud Browser](https://www.maxthon.com) and [Surfly](https://www.surfly.com)) and OS/container software largely obsolete. They are slow, clunky, and a privacy nightmare, but they still have much enterprise use. When I make my browser ports add sync features and policies, the same type of audience would appreciate Browser Ports tech. 
- For everyday web surfers, the web proxies can be repurposed to make more powerful translators (like [Kagi](https://translate.kagi.com) and [Google](https://translate.google.com) Translate) and web annotators like [Hypothesis](https://web.hypothes.is). These already use a form of web proxies but are only suitable for static sites for the most part. When you combine this with a secure and primarily feature-complete web proxy, these projects immediately become much more helpful.
- The same web proxy technology can also be used to do things like embed specific content and data from other sites and call CORS-restricted/private APIs
  - Running a website inside of a website, inside of a sandbox, in where, you have access to the entire window object and DOM, brings limitless possibilites. You could web proxy any website, modify the frontend how you please, and let others use it by linking to your website. You could do this to make mods for web games as an example.
  - You could also use automate tasks for the user and do things like authenticate with sites that don't support external oauth integrations by having them login and then executing the login flow with an invisible iframe that interacts with the login site inside of the web proxy. This is easier to use for the user, compared to telling them how to to login to a site and extract their token.
 - It should also help school kids with restricted devices and those who can't afford their computers (and use public computers) to sync their work and run the dev software they need, especially in a web os scenario. While I understand workplace/school device restrictions are there for a reason, they often hinder work in the process.
- I can imagine these web extension and userscript emulators in Proxy Middleware can be used to demo a web extension and userscript on a real-world site before installing 
- The same abilities that AeroSandbox has to fake anything that happens inside the DOM and the site APIs are so powerful. It's the essence of how *StealthBlock*, *Web Containers for Chrome*, and *Web Recorder*s will work. 

## Projects that will be finished (in estimated order of project completion)

1. [ ] [FmtErr](https://github.com/Browser-Ports/FmtErr): Some Classes and functions to wrap Runtime validation and Result libraries for TS so that exceptions are handled in a consistent way for Browser Port projects. Not much to worry about.
2. [ ] [IPC-Proxy](https://github.com/Browser-Ports/IPCProxy): This is important because when you deal with Browser technology, you need to manage and control isolated contexts for things like add-ons, and you can consider IPC Proxy to glue everything together. This is the project that will make handling IPC in the web fun again! IPC Proxy will let you import/export (like modules) any object from any context regardless of what it is using weak references / `FinalizationRegistry`, a ton of listeners and serialized data passed through them that are killed when they aren't needed anymore, and ES6 proxies wrapping all the imports. This will be easy to adapt and have integrations for all sorts of communication types like `postMessage` <-> `addEventListener`, `BroadcastChannel` <-> `BroadcastChannel`, and all of that with extra support for environments such as code sandboxes where you can only interact with I/O as strings (looking at [NodeBox](https://github.com/Sandpack/nodebox-runtime), which mean the data will be able to be serialized to just strings (typically with JSON) and not just any transferrable object for IPC. It will be that flexible. I feel this would become the most complex project in browser ports despite having some of the least LOC. It's great that the complexity would be contained in these abstractions and not be suffered in the other repos.
3. [ ] [MV3 polyfills for MV2](https://github.com/Browser-Ports/MV2-Polyfills-for-MV3): Exactly what you think it is. I won't disclose how it works until it is ready to release. I'm primarily saving it for when MV2 extensions are fully removed from the Chrome Web Store.
4. [ ] [StealthBlock](https://github.com/Browser-Ports/StealthBlock): Soon to be the first-of-its-kind undetectable adblocker powered by web sandboxing technologies
   1. [ ] Web Extension implementation
   2. [ ] Userscript Implementation
5. [ ] The Proxy Middleware demo web extension implementation will make testing Proxy Middleware much easier. For example, you don't need a web proxy, and it will have live-debugging HMR support, making the [Proxy Middleware spec](https://github.com/Browser-Ports/proxy-middleware) much more manageable.
6. [ ] The first Proxy Middleware repos (like [proxy-middleware-BP](https://github.com/Browser-Ports/proxy-middleware-BP)), a store frontend for installing Proxy Middleware with repo switching support, and the 
7. [ ] [Electron Ports](https://github.com/Browser-Ports/Electron-Ports) (will only have partial support for what I need and only gain in features as I need them). While this will be made for the browser ports, it will have a lot of utility and, except for a few things (like custom title bars in the PWA version), can completely replace Electron's runtime as a lighter alternative that is easy to develop.
   1. [ ] Electron in a PWA (as a PWA where you can install and mount Electron apps)
   2. [ ] Electron in Anura (mainlined into the repo)
   3. [ ] Electron in Puter (as a runner app and Driver)
8. [ ] A Proxy Middleware plugin for Anura
9. [ ] Web Containers for Chrome: This project will repurpose AeroSandbox's storage isolation features to make it so that you can make Web Containers work in Chromium browsers
10. [ ] A ScramJet + AeroSandbox hybrid that supplements ScramJet with the web feature support that is missing
11. [ ] FoxyWeb: A port of Firefox to the web (website, PWA, and web os) with Electron, Electron Ports, Proxy Middleware, WASM, and IPC-Proxy as the glue. I will start by gradually implementing sandboxing code and Proxy Middleware to port the Firefox XPCom APIs and ChromeUtils API, and then I will begin implementing web extension support. The APIs will work by injecting IPC-Proxy into every new client (browsing context) (FoxyWeb will use `webview` in Electron) so that the extension APIs can be reimplemented by running code and calling native web APIs from the perspective of each client and wrapping the Electron APIs, which would also be implemented similarly.
    1. [ ] Mounting the assets from Omni.ja for `resources://` and `chrome://` using Proxy Middleware response handlers
    2. [ ] ChromeUtils and XPComUtils lazy loading/importing
    3. [ ] XPCom APIs
    4. [ ] Web Extension APIs
        1. [ ] Firefox
        2. [ ] Chrome - using [webextension-polyfill](https://github.com/mozilla/webextension-polyfill) as a base
        3. [ ] Polyfills for Web Extension API used in other browsers: [webextension-polyfill-extended](https://github.com/Browser-Ports/webextension-polyfill-extended)
12. [ ] More Electron Ports work (supplemental): Client-only Tauri/Neutralino.js API shims to the Electron Ports APIs
13. [ ] FowardCompat: On-demand polyfills that get injected whenever a site needs it. It will work as a Userscript or Proxy Middleware. It will also be used for FoxyWeb so that accurate emulation mode can work (as a custom preference on about:preferences), which will make it so that inside of each browsing context, the web features that your browser supports that Firefox doesn't will be removed, and the web features that your browser doesn't support that Firefox does will be supplemented by polyfills. It will use [caniuse-db](https://www.npmjs.com/package/caniuse-db) and have its own polyfills database to apply based on your user agent. It will also make using legacy browsers in the modern era more plausible.
14. [ ] Web Recorder: Will be able to archive sites locally or view archives from the Wayback Machine. One of the advantages of using the archive sites locally is that it will also archive AJAX network requests to APIs, this is important because of a "replay" feature, which will serve all of the same assets from around the same time as the archive main navigation request and API records. The user will be encouraged not to upload archives where he/she is logged-in (because of Tokens) or is inputting personal data. Cookies will be stripped. With this replay feature, whenever a request is sent to an API, an LLM would be trained on requests for APIs on that current domain and try to guess what it would be. Additionally, it will have support for attempting to automatically adapt the APIs for an old frontend of a site to the new APIs of that site so that if you prefer the old feel of a site, you could still try to use it in the modern way. AI would just be guessing how to adapt the old API requests to the new ones, but that is not foolproof, so it would also be possible to write a custom format (Proxy Middleware or simple RegExp) that lets you rewrite network requests with replacements that "adapt" it manually (like patching it).
15. [ ] Ferrochrome: A partial port/reimplementation of Chromium to the web. I don't know if this will ever see the light of day. FoxyWeb is the priority right now.
16. [ ] Fork PWAsForFirefox to support tabbed PWAs with iframes and Firefox's UI components to add tabs