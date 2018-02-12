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

Key turnoffs that imact conversions: 

 * slow page loads
 * poor user experience 
 * (cellular) network constraints (e.g., bandwidth)


---
### [Cut load times <br/> with Developer Tools](https://academy.exceedlms.com/student/path/2967#)

 * What is [the render tree](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-tree-construction)?
 * What [slows down](https://developers.google.com/web/fundamentals/performance/rail) websites?
 * What are [DevTools?](https://developers.google.com/web/tools/chrome-devtools/)?
 * How can DevTools [debug perf issues](https://developers.google.com/web/tools/chrome-devtools/network-performance/)?

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

 * What are key website perf metrics?
 * What is Lie-Fi? Why does it matter?
 * What tools help emulate UX for Lie-Fi? 
 * What tools help diagnose perf issues?

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

Read [Optimizing Performance Under Varying Network Conditions](https://developers.google.com/web/tools/chrome-devtools/network-performance/network-conditions)

---
### [Optimize <br/> mobile site transfer size](https://academy.exceedlms.com/student/path/2967#)

<!-- Speaker Notes -->
Note:


---
### [Optimize <br/> images and fonts](https://academy.exceedlms.com/student/path/2967#)

<!-- Speaker Notes -->
Note:


---
### [Focus on <br/> mobile user experience](https://academy.exceedlms.com/student/path/2967#)

<!-- Speaker Notes -->
Note:


---
### [Deliver <br/> user-centered mobile experience](https://academy.exceedlms.com/student/path/2967#)

<!-- Speaker Notes -->
Note:


---
### [Make mobile sites that <br/> drive conversions](https://academy.exceedlms.com/student/path/2967#)

<!-- Speaker Notes -->
Note:


---
### [Test and optimize <br/> mobile experiences ](https://academy.exceedlms.com/student/path/2967#)

<!-- Speaker Notes -->
Note:


---
### [Create super fast sites <br/> with AMP](https://academy.exceedlms.com/student/path/2967#)

<!-- Speaker Notes -->
Note:


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
## 1. Value Proposition 
 
#### <span class="white"> <a href="https://support.google.com/partners/answer/7327828"> Mobile Sites & Why They Matter</a> </span>


---
## 2. Site Performance
 
#### <span class="white"> <a href="https://support.google.com/partners/answer/7327828"> Improving mobile site speed</a> </span>


---
## 3. User Experience

#### <span class="white">  <a href="https://support.google.com/partners/answer/7327828"> Creating an effective mobile UX</a> </span>



---
## 4. Tech Evolution 
 
#### <span class="white">  <a href="https://support.google.com/partners/answer/7327828"> Advanced Web Technologies </a> </span>


---
## 5. Certification 
 
#### <span class="white">  <a href="https://support.google.com/partners/answer/7358899"> Taking the Assessment </a> </span>

---?image=assets/image/background.jpg&opacity=100
# <span class="white"> GDGNYC <br/> Study Jams </span>

### <a href="https://gdgny.herokuapp.com"> Join us on Slack! </span>

---
