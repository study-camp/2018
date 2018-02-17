---?image=assets/image/background.jpg&opacity=100
# <span class="white"> Mobile Site <br/> Certification </span>

### <span class="white"> GDGNYC Study Guide </span>



---
## <a href="http://bit.ly/gdgnyc-cloud-studyjams-2018"> Know the <br> Agenda </a>

 * Prepare for Assessment
 * Timed Exam = _90 minutes_
 * Pass Score = _80%_ 
 * Retakes = _After 1 day_



---?image=assets/image/background.jpg&opacity=100
## <span class="white"> Study Guide A </span>
 
#### <a href="https://academy.exceedlms.com/student/path/2967"> Academy Of Ads Learning Path </a>

![GDG Study Jams](assets/image/logo.png)



---
### [Win customers <br/> with mobile sites](https://academy.exceedlms.com/student/path/2967#)

  * What is a mobile website?
  * How does the user benefit?
  * How does the owner benefit?
  * What impacts user conversions?

<!-- Speaker Notes -->
Note:

_Time: 5 mins_

Definition:

 * website tailored for mobile device
 * accessed via browser on phones

Benefits to user:

 * easy to discover (no pre-install)
 * intuitive to use (familiar UI/UX)
 * readily available on phones

Benefits to owner:

 * lower development/maintenance costs
 * high usability * tracking
 * single codebase for cross-platform reach

Key turnoffs that impact conversions: 

 * slow page loads
 * poor user experience 
 * (cellular) network constraints (e.g., bandwidth)




---
### [Cut load times <br/> with Developer Tools](https://academy.exceedlms.com/student/path/2967#)

 * What is [the render tree](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-tree-construction)?
 * What [slows down](https://developers.google.com/web/fundamentals/performance/rail) websites?
 * What are [DevTools?](https://developers.google.com/web/tools/chrome-devtools/)?
 * How can DevTools [diagnose slow-downs](https://developers.google.com/web/tools/chrome-devtools/network-performance/)?

<!-- Speaker Notes -->
Note:

_Time: 15 mins_

Use Chrome DevTools to debug delays:

 * _Inspect_ Website, open _Network_ tab
 * Enable _Capture Screenshots_
 * Check _Disable Cache_
 * Set Online to _Slow 3G_
 * Now reload page
 * Check _Finish_ and _Load_ times in footer
 * Check _DOMContentLoaded_ time in footer
 * Check _Waterfall_ green (TTFB) & blue (download) 

Causes of delay

 * Identify items with large blue waterfalls. These indicate large download times that need to be optimized (e.g., compress or scale image, minimize scripts etc.)
 * DOMContentLoaded is effectively 'idle' browser time while it waits for DOM to be ready. Likely culprit is JavaScript file (parser blocking). Make these async and move to end of page <body> to speed up loading of HTML.

Understanding render trees

 * DOM = document object model (structure)
 * CSSOM = CSS object model (styling)
 * render tree = browser process of interpreting DOM/CSSOM
    + first receive data bytes (HTML and CSS)
    + convert bytes into objects (DOM and CSSOM)
    + relate DOM (elements) with CSSOM (style)
    + place DOM objects on page, apply CSSOM styles
    + page is now "rendered"
 
Understanding layout impact

  * Layout determines "reflows" with device orientation or content changes
  * Poor configurations = high reflow costs
  * Complex animations = high reflow costs
  * Goal = minimize reflows!!

Debugging critical rendering path delays

  * Switch to _Performance_ tab in DevTools
  * Click "Record" to start recording events
  * Reload page to capture all events for initial render
  * Stop recording, filter by event name to see data
    + Parse HTML = time for building DOM
    + Recalculate Style = time for building CSSOM
    + Paint = time for updating screen area for view
    + Composite Layer = time for creating final view by combining multiple elements that influence that section of view 

Bottom line:
Chrome DevTools (CDT) helps detect different sources of latency in your website, and provides tools to debug causes of those performance issues. It does NOT however fix them for you.




---
### [Speed up <br/> mobile site rendering](https://academy.exceedlms.com/student/path/2967#)

 * What is the [critical rendering path?](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/)
 * How can you [measure](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/measure-crp) it?
 * How can you [analyze](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp) it?
 * How can you [optimize](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path) it?

<!-- Speaker Notes -->
Note:

_Time: 20 mins_

Speeding up websites requires streamlining the critical rendering path by removing common issues that create slowdowns:
 * Running blocking scripts that are non critical
 * Loading resources that are non critical

What are the goals?

 * Limit critical resources. These are resources that appear _before_ the body of the page.
 * Shorten critical path. Several large resources in sequence can cause drag (gfetch time + load/apply time). Identify ways to reduce sequences.
 * Minimize critical bytes. Separate into "must load first" and "can load later" parts of website (e.g., above the fold vs. require scroll to view). Optimize sizes (file compression, format selection etc.)

Four Step Process:

 1. ANALYZE. Use DevTools to visualize number of resources, bytes and overall length of critical path.
 2. MINIMIZE. Eliminate resources from critical path. Use _async_ or _defer_ for JavaScript that is not needed in initial render. For non-critical files (e.g., styles, images) remove from markup (HTML) and instead use JavaScript to lazy-load them after.
 3. OPTIMIZE. Use compression tools, smart file format choices and efficient coding patterns to reduce volume of critical bytes.
 4. REORDER. Set critical assets to download as early as possible so as to speed up critical rendering path.

JavaScript Optimization:

 * Rewrite JavaScript for faster code execution
 * Defer download of script file so essential HTML loads first
 * Mark script as async so webpage renders while script is processed 



---
### [Key metrics <br/> for testing your site](https://academy.exceedlms.com/student/path/2967#)

 * What are key perf metrics?
 * What is [Lie-Fi](https://developers.google.com/web/fundamentals/performance/poor-connectivity/)?
 * How can you [emulate Lie-Fi UX](https://developers.google.com/web/tools/chrome-devtools/network-performance/network-conditions)? 
 * How can CDT diagnose network issues?

<!-- Speaker Notes -->
Note:

_Time: 20 mins_

Poor website performance can lead to higher user bounce rates (site departures) and lower conversion rates (site interactions of value)

What are the criteria for site performance?

 * Speed Index. Score averaging time at which various parts of page are displayed. Lower (below 5000) is better. 
 * Total requests. Number of resource requests (to server) to build a page. Lower (80-100) is better. Combine/eliminate requests to achieve it.
 * Page weight. Total size of resources to build page. Should not be larger than 1 MB. Remove/compress resources to achieve this.

What is Lie-Fi?

 * Perception of good network access when reality is that network issues exist
 * Network issues include: intermittent connectivity, router issues, server issues, MSO issues etc.
 * Any delays in request/response path contribute to Lie-Fi.

What tools can help you emulate user experience?

 * *Browser Tools.* Use CDT Network Panel to test upload/download speeds and round-trip times under various conditions.
 * *System Tools.* Use Network Link Conditioner on Mac (available via XCode Hardware IO tools) to simulate various network conditions.
 * *Device Emulator.* Android Emulator allows network conditions to be simulated via settings, for both web apps & hybrid web apps
 * *Location Services.* [WebPageTest](https://www.webpagetest.org/) runs perf tests on your site from various physical locations to provide real feedback on performance at those location.
 * *Impairment Apps.* Facebook and others have applications that can be used to shape traffic and emulate impaired network conditions. 

How can Chrome DevTools (CDT) diagnose perf issues?
 * Inspect site with CDT. Open Network panel.
 * Capture Screenshots | Disable Cache | Poor 3G Network
 * Reload page | Check load times | Check waterfall 
 * Identify slow scripts | Mark async or defer
 * Identify large images | Change format (SVG) or optimize (compress)
 * Retest page load | Iterate.




---
### [Optimize <br/> mobile site transfer size](https://academy.exceedlms.com/student/path/2967#)

 * How to eliminate unused resources?
 * How to reduce size of downloaded assets?

<!-- Speaker Notes -->
Note:

_Time: 22 mins_

The fastest resource is the one _not_ sent. _How can you identify and eliminate unused resources?_
 * Carousels. Are you downloading more images that you need to (if no one ever goes beyond the main one?)
 * Social Media Integrations. Is your site pulling down real-time updates that have attached media? Are those optimized? Do we need this or is there a better way?
 
Understanding data compression. _How can you reduce the size of transferred assets to improve perfomance?_
 * Smaller files through minification. Remove comments, remove duplicates, collapse common containers, remove extraneous spaces.
 * [Optimize encoding and transfer of text-based assets](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer#minification-preprocessing--context-specific-optimizations)



---
### [Optimize <br/> images and fonts](https://academy.exceedlms.com/student/path/2967#)

 * How to optimize fonts?
 * How to optimize images?
 * How to optimize caching strategy?

<!-- Speaker Notes -->
Note:

_Time: 20 mins_

Web fonts and images improve design but add latency. Let's optimize this by eliminating them (if possible), optimizing them (for efficiency) and caching them optimally (for reuse)

How can you optimize images?

 * Minify and compress vector images. SVG (Scalable Vector Graphics) are ideal for multi-device, high-resolution, compact image representation.
 * Remove unnecessary image metadata. Drawing apps may pack unnecessary metadata into the images. Remove and/or compress for efficiency.
 * Pick best raster image format. Dial down quality or select formats that optimize for downloads (& byte savings) without significantly impacting experience.
 * Resize on server. Create scaled versions of images on server for optimal size/resolutions that are closest to the "natural" size of the displayed element.
 * Automate, automate, automate. Invest in tools and processes that auto-compress images, auto-minify/compress files etc.

How can you optimize your fonts?

 * Optimized fonts, combined with loading strategy, is ideal.
 * Best practices
    + don't use too many fonts
    + minimize number of used variants per font
    + fonts can be split into subsets with just the needed glyphs
    + deliver optimized font formats to browser (multiple formats may exist)
    + fonts are static resources. cache/revalidate intelligently
    + explore [_Font Loading API_](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Font_Loading_API) for custom rendering/timeout strategies

How can you optimize caching strategy?

 * Consistent URLs for same content to leverage caching/reuse
 * [ETag Header](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/ETag) - Validation tokens eliminate need to reload (if asset has not changed on server)
 * Intermediaries - what assets can be cached by intermediaries like CDNs? (Ideally content that is static and non-user specific)
 * Cache lifetime - determine default cache max-age for each item to tradeoff fetch times against freshness
 * Cache hierarchy - resource URLs with short or no-cache lifetimes for HTML documents, ensures pages are freshly loaded but the assets they use are cached optimally
 * Churn - identify parts of code that change more frequently than others, and isolate them in their own file. Now the rest can be loaded once and cached, and only the small changing subset reloaded on-demand.
 



---
### [Focus on <br/> mobile user experience](https://academy.exceedlms.com/student/path/2967#)

 * What defines good mobile UX?
 * How can you motivate conversions?
 * What configuration techniques should I use?

<!-- Speaker Notes -->
Note:

What defines a good user experience?
 * Clear navigational cues (sitemaps)
 * Conspicuous search bar (quick finds)
 * Rich & usable options (browse & filter)

How can you motivate conversions?
 * Eliminate number of clicks for desired outcome
 * Eliminate unnecessary data entry (auto-fill forms)
 * Reduce user friction (e.g., proceed as guest)
 
How can I configure mobile sites (for diverse screens)

 Pick strategy based on your requirement: 
  * should URL be the same?
  * should HTML (code) be the same?

Strategy Options are:
 * Responsive web design. URL & HTML stay the same; layout reflows to suit different screen sizes.
 * Dynamic serving. URL stays the same but HTML differs for each device type. Achieved by having server dynamically return relevant HTML for same URL request, based on client context (e.g., user-agent, device type etc.)
 * Separate URLs.  URL changes for each device type. Effectively, the site routes user to different URLs (with different HTML) using HTTP redirects, based on detected client context.

Use the [TestMySite](https://testmysite.thinkwithgoogle.com/) service to check your site's UX for mobile usability and performance.
  


---
### [Deliver <br/> user-centered mobile experience](https://academy.exceedlms.com/student/path/2967#)

 * How to design the Homepage?
 * How to design Site Navigation?
 * How to design Site Search?

<!-- Speaker Notes -->
Note:

Key focus is connecting user to content they want. Mobile sites should optimize for this by focusing on:
 * Design of Homepage
 * Design of Navigation
 * Design of Search

Process:
 * Prioritize what's important
 * Make priorities prominent on page
 * Fewest menu items (on mobile)
 * Consistent across pages (e.g., logo at top left)
 * Intelligent site search

Designing site Search
 * Make search button VISIBLE
 * Provide RELEVANT results
 * Simplify data ENTRY (auto-complete, spellcheck)
 * Offer FILTERS (refine search up front)
 * Guide users to BETTER results (recommendations, ask contextual questions ahead of time)

Mobile Usability and Form Factor
 * Optimize entire site for mobile (not hybrid mobile/desktop)
 * Offer the right zoom (design so user doesn't need to change size on demand! But offer richer views if they do)
 * Stay in the same window (no launching new tab) - users need to feel they are in the same app, and find way back
 * Don't say "full site" - say "desktop site" (else users think mobile is limited in some way)
 * Be clear about location - don't autodetect. Instead provide calls to action that indicate why we want their permission to use location (e..g., find near me)



---
### [Make mobile sites that <br/> drive conversions](https://academy.exceedlms.com/student/path/2967#)

 * How can you give users more control of UX?
 * How can you design to optimize conversions?
 * How can you reduce friction for data entry?
 * What makes a [good mobile site](https://developers.google.com/web/fundamentals/getting-started/principles/)?

<!-- Speaker Notes -->
Note:

Putting users in control of UX means giving them choices and guidance (instead of making choices for them) 
 * Choice to register. Allow guest modes.
 * Choice of formats for data entry. Pick vs. type.
 * Guidance in data entry. Auto-fill forms.

Design for max conversions
 * Make registration optional. "Try before buy".
 * Make data entry easy. Save progress. Prompt reuse.
 * Reduce completion effort. Click-to-call. Share-to-self.
 
Streamlining forms. Frictionless data entry.
 * Set types per input. Validation & contextual keyboards!
 * Avoid text input if possible. Drop-downs, toggles, checkboxes.
 * Auto-fill data. Save & reuse relevant context.
 * Auto-advance in form. Move focus seamlessly.
 * Provide visual cues. e.g., use calendars for dates.
 * Minimize errors. Validate inputs, show useful prompts/errors
 * Make forms efficient. Remove redundancy. Show progress. Auto-fill.

---
### [Test and optimize <br/> mobile experiences ](https://academy.exceedlms.com/student/path/2967#)

 * What is A/B Testing (ABT)?
 * What is Google Analytics (GA)?
 * How can ABT drive design decisions?
 * How can GA drive perf insights & optimization?
 * Learn about: Google [Optimize](https://support.google.com/360suite/optimize/answer/6211921) and [Analytics](https://support.google.com/analytics/answer/1008015?hl=en&ref_topic=3544906)

 
<!-- Speaker Notes -->
Note:

How do we normally make a decision?
 * Executive approach. One person decides.
 * Democratic approach. Everyone votes and majority wins.
 * Data-driven approach. Run experiments, use insights.

Data-driven approach: A/B Testing
 * Decide between two (or more) options
 * Serve each option randomly to a subset of site visitors.
 * Keep context consistent (e.g., same time of day for all)
 * Tools: Manage testing with [Google Optimize](https://www.google.com/analytics/optimize/)

Measuring performance: Google Analytics
 * Bounce rate: user left landing page without interacting
 * Device usage: what devices/OS are used, do they impact perf? 
 * Browser/Screen Data: study impact of platform or screen resolution
 * Site search reprots: Usage of search, related conversion rates (show efficacy of search and identify areas for improving navigation)
 * Shopping behavior analysis: Purchase funnel, where are users abandoning process (and why, based on possible causes at each step)
 * Checkout behavior analysis: Checkout funnel (key conversion), where are userrs abandoning it (and why, e.g., registration as deal-breaker)
 



---
### [Create super fast sites <br/> with AMP](https://academy.exceedlms.com/student/path/2967#)

  * What are Accelerated Mobile Pages (AMP)?
  * What is [AMP HTML](https://www.ampproject.org/docs/reference/spec)?
  * What is the AMP Cache?
  * [How does AMP work](https://www.ampproject.org/learn/how-amp-works/) to deliver content faster?

<!-- Speaker Notes -->
Note:
Accelerated Mobile Pages (AMP) are _static content pages_ that are streamlined for fast (almost instantaneous) loads
 * built on open web standards
 * normal web pages with restrictions and add-ons
 * use AMP HTML (= standard HTML _extended with custom AMP properties_)
 * use AMP tags (= custom elements) for enhanced behaviors
 
AMP Features:
 * AMP JavaScript library. Allows only async JS so nothing in page can block rendering.
 * AMP Cache. Proxy-based CDN that caches AMP HTML pages, validates content and optimizes performance automatically at the edge.

How does AMP Work?
 * All resources (images, iframes) MUST specify their sizes in the HTML.
 * AMP now determines resource size and position first, and prioritizes downloads of important or "visible" items first.
 * All CSS styles MUST be inline so there is no waiting for CSS.
 * AMP does page layout before all resources are downloaded
 * No blocking extensions (embeds). Instead use equivalent AMP extensions that make requests without blocking page render.
 * All AMP pages using third-party JS MUST be sandboxed into iframes so they don't block execution of the main page.


---
### [Create <br/> Progressive Web Apps](https://academy.exceedlms.com/student/path/2967#)

<!-- Speaker Notes -->
Note:



---
### [Engage users <br/> with APIs](https://academy.exceedlms.com/student/path/2967#)

<!-- Speaker Notes -->
Note:



---?image=assets/image/background.jpg&opacity=100
## <span class="white"> Study Guide B </span>
 
#### <a href="https://support.google.com/partners/answer/7327828"> Google Partners Assessment Guide </a>

![GDG Study Jams](assets/image/logo.png)



---
## <a href="https://support.google.com/partners/answer/7358899?hl=en&ref_topic=7359299">Preparing for <br> Assessment</a>

 * What is the value proposition?
 * How can you improve website speed? 
 * How can you create effective UX?
 * About advanced web technologies
 

---
## <a href="https://support.google.com/partners/answer/7358899?hl=en&ref_topic=7359299">Preparing for <br> Assessment</a>

 1. (Proposition) <a href="https://support.google.com/partners/answer/7327828"> Mobile Sites & Why They Matter</a>
 2. (Performance) <a href="https://support.google.com/partners/answer/7327828"> Improving mobile site speed</a>
 3. (Experience) <a href="https://support.google.com/partners/answer/7327828"> Creating an effective mobile UX</a>
 4. (Evolution) <a href="https://support.google.com/partners/answer/7327828"> Advanced Web Technologies </a>
 

---
## 5. Recommended Reading

<small>
  <ol>
    <li> <a href="https://www.thinkwithgoogle.com/articles/mobile-page-speed-new-industry-benchmarks.html">Find Out How You Stack Up to New Industry Benchmarks for Mobile Page Speed</a></li>
    <li> <a href="https://www.thinkwithgoogle.com/articles/mobile-retail-apps-and-sites-designing-better-experience-for-shoppers.html"> Mobile Retail Apps and Sites: Designing a Better Experience for Shoppers </a></li>
    <li><a href="https://developers.google.com/web/tools/chrome-devtools/network-performance/">Get Started with Analyzing Network Performance in Chrome DevTools</a></li>
    <li><a href="https://www.youtube.com/playlist?list=PLAwxTw4SYaPmKmNX-INgcxQWf30KuWa_A">Udacity Web Performance Optimization</a></li>
    <li><a href="https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path">Optimizing the Critical Rendering Path</a></li>
    <li><a href="https://developers.google.com/web/tools/chrome-devtools/network-performance/network-conditions">Optimize Performance Under Varying Network Conditions</a></li>
    <li><a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer#minification-preprocessing--context-specific-optimizations">Optimizing Encoding and Transfer Size of Text-Based Assets</a></li>
    <li><a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization">Image Optimization</a></li>
    <li><a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/webfont-optimization">Web Font Optimization</a></li>
    <li><a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching"></a>HTTP Caching</li>
    <li><a href="https://testmysite.thinkwithgoogle.com/">Test how mobile-friendly your site is</a></li>
    <li><a href="https://developers.google.com/web/fundamentals/getting-started/principles/"></a>What makes a good mobile website?</li>
    <li><a href="https://support.google.com/360suite/optimize/answer/6211921">Set up Optimize</a></li>
    <li><a href="https://support.google.com/analytics/answer/1008015?hl=en&ref_topic=3544906"></a>Get Started with Analytics</li>
    <li><a href="https://www.ampproject.org/docs/reference/spec">AMP HTML Specification</a></li>
    <li><a href="https://www.ampproject.org/learn/how-amp-works/">How AMP Works</a></li>
    <li><a href="https://www.ampproject.org/docs/get_started/create">Create your first AMP page</a></li>
    <li><a href="https://developers.google.com/web/progressive-web-apps/">Progressive Web Apps</a></li>
    <li><a href="https://developers.google.com/web/fundamentals/getting-started/primers/promises"></a>JavaScript Promises</li>
    <li><a href="https://developers.google.com/web/fundamentals/discovery-and-monetization/payment-request/">Payment Request API: An Integration Guide</a></li>
  </ol>
</small>

---
## 6. Certification 
 
#### <span class="white">  <a href="https://support.google.com/partners/answer/7358899"> Taking the Assessment </a> </span>


<!-- Speaker Notes -->
Note:

My experiences with taking the assessment:


---?image=assets/image/background.jpg&opacity=100
# <span class="white"> GDGNYC <br/> Study Jams </span>

### <a href="https://gdgny.herokuapp.com"> Join us on Slack! </span>

---
