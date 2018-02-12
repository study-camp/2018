---?image=assets/image/background.jpg&opacity=100
# <span class="white"> Mobile Site <br/> Certification </span>

### <span class="white"> GDGNYC Study Guide </span>

---
## <a href="http://bit.ly/gdgnyc-cloud-studyjams-2018"> Know the <br> Agenda </a>

 * Prepare for Assessment
 * Timed Exam = _90 minutes_
 * Pass Score = _80%_ 
 * Retakes = _After 1 day_

---
## <a href="https://support.google.com/partners/answer/7358899?hl=en&ref_topic=7359299">Prepare for <br> Assessment</a>

 * Understanding Value Proposition
 * Improving Website Speed
 * Creating Effective UX
 * Advanced Web Technologies
 

---?image=assets/image/background.jpg&opacity=100
<br/><br/><br/>
## <span class="white"> 1. Value Proposition </span>
 
#### <span class="white"> <a href="https://support.google.com/partners/answer/7327828"> Mobile Sites & Why They Matter</a> </span>


---?image=assets/image/background.jpg&opacity=100
<br/><br/><br/>
## <span class="white"> 2. Site Performance </span>
 
#### <span class="white"> <a href="https://support.google.com/partners/answer/7327828"> Improving mobile site speed</a> </span>


---?image=assets/image/background.jpg&opacity=100
<br/><br/><br/>
## <span class="white"> 3. User Experience </span>

#### <span class="white">  <a href="https://support.google.com/partners/answer/7327828"> Creating an effective mobile UX</a> </span>



---?image=assets/image/background.jpg&opacity=100
<br/><br/><br/>
## <span class="white"> 4. Tech Evolution </span>
 
#### <span class="white">  <a href="https://support.google.com/partners/answer/7327828"> Advanced Web Technologies </a> </span>


---?image=assets/image/background.jpg&opacity=100
<br/><br/><br/>
## <span class="white"> 5. Certification </span>
 
#### <span class="white">  <a href="https://support.google.com/partners/answer/7358899"> Taking the Assessment </a> </span>


---
## Academy of Ads
 
#### <a href="https://academy.exceedlms.com/student/path/2967"> Academy Study Path </a>

![GDG Study Jams](assets/image/logo.png)

---
### [Win customers <br/> with mobile sites](https://academy.exceedlms.com/student/path/2967#)

  * What is a mobile website?
  * How does user benefit?
  * How does owner benefit?
  * What impacts conversions?

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

 * What is the render tree?
 * What slows down mobile websites?
 * Can DevTools help identify causes?
 * Can DevTools help automate fixes?

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
DevTools helps detect different sources of latency in your website, and provides tools to debug causes of those performance issues. It does NOT however fix them for you.


---
### [Speed up <br/> mobile site rendering](https://academy.exceedlms.com/student/path/2967#)

<!-- Speaker Notes -->
Note:


---
### [Key metrics <br/> for testing your site](https://academy.exceedlms.com/student/path/2967#)

<!-- Speaker Notes -->
Note:


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


---
