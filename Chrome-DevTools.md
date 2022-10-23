# Notes on Chrome DevTools

Notes from various videos combined into sections for each Tab. As a result, I will have repeats until I go back and edit each section.

<div id="back-to-top"></div>

## Table of Contents

1. [GENERAL NOTES](#general-notes)
1. [ELEMENTS TAB](#elements-tab)
   1. [STYLES Pane](#styles-pane)
1. [CONSOLE TAB](#console-tab)
1. [PERFORMANCE TAB](#performance-tab)
1. [SOURCES TAB](#sources-tab)
1. [NETWORK TAB](#network-tab)
1. [APPLICATION TAB](#application-tab)
1. [TIMELINE TAB](#timeline-tab)
1. [SECURITY TAB](#security-tab)
1. [MEMORY TAB](#security-tab)
1. [LIGHTHOUSE TAB](#lighthouse-tab)

## GENERAL NOTES

Main tabs:

| Tab name    | Tab name    | Tab name   |
| :---------- | :---------- | :--------- |
| Elements    | Console     | Sources    |
| Network     | Performance | Memory     |
| Application | Security    | Lighthouse |

3 vertical dots > `More tools` (22 tools):

| Tab name             | Tab name            | Tab name                 |
| :------------------- | :------------------ | :----------------------- |
| Animations           | Changes             | Coverage                 |
| CSS Overview         | Developer Resources | Issues                   |
| JavaScript Profiler  | Layers              | Media                    |
| Memory Inspector     | Network Conditions  | Network Request Blocking |
| Performance Insights | Performance Monitor | Quick Source             |
| Recorder             | Rendering           | Search                   |
| Security             | Sensors             | WebAudio                 |
| WebAuthn             | -                   | -                        |

- `F12` or `CTRL+SHIFT+I` to open dev tools, or right-click > inspect
- Some tabs show the same thing like execution time, file names
- You can choose where to have the tabs and you can resize all the panes
- Click the `Toggle device toolbar` icon and choose either `Responsive` or a particular device - it also creates a bubble pop-up showing you the styles
- You can also click areas of the top gray bar in the web page view for different devices view, or to change from landscape to portrait
- Toggle the `Toggle device toolbar` button to get back into normal viewing mode
- Devices can also be selected by clicking the top gear icon > Devices
- 3 vertical dots > Run command - Why?
- While in the various tabs you can hit `ESC` to open the Console Drawer while remaining in that tab - hit `ESC` again to close it

Top Gear icon options/settings:

| Setting name | Setting name | Setting name |
| :----------- | :----------- | :----------- |
| Preferences  | Workspaces   | Experiments  |
| Ignore List  | Devices      | Throttling   |
| Locations    | Shortcuts    | -            |

- `user agent stylesheet` - these are styles added by the web browser. The best way to override them is to put your own styles on those elements.

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## ELEMENTS TAB

- You can test out different elements or styles, get styles for an element, copy the HTML for an element, and more
- There are _sub-tabs/views_ labeled `Styles`, `Computed`, `Layout`, `Event Listeners`, `DOM Breakpoints`, `Properties`, and `Accessibility`
- The `Computed` subtab (also at bottome of `Styles`) is very useful to see and edit box model settings for an element: border, margin and padding values
- top left: 1. `Select an element in the page to inspect it` button, 2. `Toggle device toolbar` button - the select element tool will allow you to click on an element and highlight it's details in the elements and styles panes
- You can also hover over the HTML to highlight the elements on the page
- I personally have no interest in changing text but adding a class to see the effect is a good idea
- You can also right-click > Add attribute to add an `id` or whatever you want
- You can right-click and select `Hide element` but no layout shift occurs to replace the element - it's not removed, only hidden
- right-click > `Edit as html` to edit the tag, id, class, etc.
- right-click > `Edit attibute` to edit any attribute - it defaults to the 1st attribute in the opening tag
- To edit an attribute other that the first, right-click over the attribute you want to edit
- right-click > `Delete element` does remove it and a layout shift occurs -
- You can also move elements and the easiest is click and drag
- Also try right-click > Expand recursively
- Select an element then right-click > :

1. `Copy` > `Copy element`: & 2. Copy > Copy outerHTML:

```html
<div id="top">
  <h1>Stunning free images &amp; royalty free stock</h1>
  <h2>Over 2.7 million+ high quality stock images, videos and music shared by our talented community.</h2>
</div>
```

3. `Copy` > `Copy selector`: `#top` - use to get a unique CSS selector for an element
4. `Copy` > `Copy JSPath`: `document.querySelector("#top")`
5. `Copy` > `Copy styles`

```css
-webkit-text-size-adjust: 100%;
color: #191b26;
font-family: Open Sans, Arial, sans-serif;
text-align: center;
margin: 0;
position: relative;
padding: 20px 20px 5px;
```

6. `Copy` > `Copy Xpath`: `//*[@id="top"]`
7. `Copy` > `Copy full Xpath`: `/html/body/div[1]/div[2]/div[1]/div[3]`

- You can add a new class, delete, hide, etc -
- You can alter your classes to see the effect or get the styles for a page you like
- `Commands` option, he did a shortcut to open a search box and type _cover_ for the command `showCoverage` I think
- Click the style sheet on the left pane and it will show you which classes are used on that page and which are not -

1. Go to the Sources tab and click the Play/Record btn and that’s how you find the unused classes
2. Note, click on a stylesheet name first

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### STYLES Pane

- You can toggle the styles by clicking the checkbox for any style - but it will turn off that class for all elements using it - that helps finding why a rule is not taking effect on the page
- To turn off a class for a specific element, select the element, then click `.cls` for class and you can toggle any of that item's classes
- `Elements` tab > `Styles` > `Computed` – all style values are shown – inherited styles are shown with reduced opacity – if you find an element with text in it you can see the rendered font at the very bottom -
- `Accessibility` tab which will show the aria labels not selected which means you should add them
- Select an element > click the `.cls` > and there is a field called `Add new class`
- As you type, classes in your stylesheet(s) will appear
- Next to `.cls` is a `+` button to add new classes: click an element > click `+` and an element selector will be created for that -
- You can also click on the color swatch to open a color picker and change the color and see the contrast ratio
- The `Computed` tab shows you the box model -it also shows you all the specific styles for the selected element
- Clicking `.hov` lets you see the styles for hover or any pseudo class and shows the effect
- If you have psuedo classes like hover, you can select the element, then click `.hov` top right and check the hover box and you can see what the element looks like when a user is hovering over it – it will show you the styles for that as well -
- You can filter for CSS props like `color` that are on the selected element
- Select an element then go to the Styles pane - at the top you will see `element.style {}`- you can enter styles for that element there
- If you see a CSS rule with strikethrough, then it is being overridden by a more specific rule - so use to remove useless css

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## CONSOLE TAB

- This is the main tab you will be in
- common to use `console.log()` to make sure you are getting what you want
- `console.dir()` is great for looking at the event object, when manipulating the DOM, and for ...
- you can add a variable name to see what the value is, whether the variable name is a function name, array name, object name, etc
- you can use the search box to narrow down what you see in the console but then you should not have that much that is coming from you. For REact though you will often see a lot of warning messages
- clicking the gear icon opens the console settings - I often check `Preserve log` when I get an error that does not output to the console with the errors.
- `console.error()` and `console.warn()` could be useful but I don't use them
- `console.table()`: looks great for objects
- `console.group()`: not sure what this is
- `console.assert()`: not sure what this is
- clear the console with the clear btn or use `console.clear()` although make sure "Preserve log" is unchecked
- the left pane separates the console messages by type
- `console.log()` is the most common console method, but `console.error()` and `console.warn()` have their place as well
- The up arrow (**&uarr;**) will cycle thru previous console commands you entered
- `$_` in the colsole gives you the returned value from the last expression unless you cleared the console
- `$0` will give the last HTML element inspected/selected and everything inside that element - `$1` will display the element before that and so on
- You can also use the `$` sign as an alias for `document.querySelector`, similar to jQuery, e.g. `$('h1').style.color = "red"`
- `console.dir()` shows a JS representation of any DOM element – like `console.dir(document)` click on the `#document` to see everything about it – then console log anything like the `URL` or `nodeType` do `console.log(document.nodeType)`
- You can create tables in the console with arrays and objects:
  - `console.table( [ { name: "jim", email: "test@test.com", age: 33 } ] )` watch the quotes though
- You can filter things out – click the down triangle next to `Default Levels` – info, warnings and errors are checked – why is mine inactive?
- `console.clear()` to clear the console
- Log things in groups – `console.group( 'someName' )` then `console.groupEnd('someName')` – then you can add console.logs in between or whatever else - when would you use this?
- NOTE: `someName` but be used in both `group` and `groupEnd`, same for below with `time` and `timeEnd`
- `console.time('For loop') `then `console.timeEnd('for loop')` then a for loop in between – when would you use this? To test how long a loop takes? It returns the total time in milliseconds
- Settings – click the gear icon and you can choose to show – can log AJAX requests (XMLHttpRequests), choose to show time stamps with your logs
- Run insertions / tests – `console.assert()` but inside a function – when would you use this?
- The syntax is `assert(assertion, obj1, obj2, ...objN)` or `assert(assertion, msg, substr1, ...substrN)` - and the object needs to be in JSON format

```js
function greaterThan(x, y) {
  console.assert(x > y, { message: "x is not greater than y" });
}
```

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## PERFORMANCE TAB

- Different from Lighthouse?
- Hit the record btn and click on btns or refresh the page info on the page performance for loading, scripting, rendering, and painting

## SOURCES TAB

- Shows a tree of all the files in the project
- This is a good tool to see the file structure for sites that are more advanced than what you are creating - **_the real world_**!
- allows you to view your files and externally loaded things like jQuery, SQL, cookies, storage, etc
- this tab is best for when you are trying to debug something – the bigger the app, the harder it is to find the issue -
- 3 panes: left are your files, center window shows the code in a file you select, he has a right 3rd pane which has breakpoints, scope, call stack for JS files and start/stop/skip buttons

  > I Had my left pane on Snippets - I had to click the “play” btn far right to open tthat 3rd pane

- click a row # to add a breakpoint – click again to remove it – or right-click – seems like you need user interaction to trigger it like a button click
- for the left pane click the >> symbol to chose Page –
- you can use the step over btn to bypass lines of code
- check all the btns
- click things like Callstack but make sure to refresh page
- it's probably best at first to create a simple js file with an alert and console log and check things out - then create a function that call other functions and use some high order array methods
- you can also have conditional breakpoints if you right-click
- in Sources you can drill to any folder and file you want – typical to do that with JS files – when you set a breakpoint and use the UI to run the code, you can then hover over your breakpooint to see what the value is and change it if you want
- refresh the page after creating a breakpoint(s) and it will stop at each breakpoint
- and then you can go to any other tab and see what's going on - THAT IS HUGE!
- YOU CAN SET YOUR BREAKPOINTS BASED ON A js EVENt, a specific line of code, on DOM manipulation,
- you can also create DOM breakpoints by going into the html file -
- there are also event listener breakpoints -
- Snippets are also in the Sources tab
- `Snippets` – if not showing, click the dbl `>>` symbols and select Snippets – click `+` for new snippet – name it, then go into the text editor to the right and try a console.log message, CTRL+s to Save or right-click to save
- To run it click the name to the right, right-click and select run – didn’t execute for me but why use this? Oh it did run but not in the console on that tab
- You can edit your code in this tab – click `Page` next to snippets or to the left of `>>` collapse any file listings > right-click in the empty field directly below > or click one of the file names to see the source code
- Right-click > add folder to workspace > select the folder that your source files are in > can make changes to your files and save them – WHY?

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## NETWORK TAB

- Network Tab: has a list of all the files for the page
- It's also where you want to look for any AJAX or fetch or API calls
- you can look at how long each part of a request is taking
- color coded so learn what each color means
- take a look at the things that took the longest time to load
- You may have to do a page refresh while in the tab to get all the files and related information
- use it to check if any calls did not go thru, and missing files, and other things for troubleshooting
- Like some of the other tabs, you will see a list of all of your files and any external sources you are using
- click on any of them to see details like `Status`, `Response headers`, `Remote address`, `cache-control`, last-modified, and more all in the Headers section/tab
- Also check out Timing and Cookies sections
- You can also click on the links to specify by JS, CSS, Img, etc.
- you can also select a file then right-click for other/more options, or at least a more visual way to access some settings and filters
- Files: shows all the files loading for that page – shows the size of the file and the time it takes to load, Waterfall, type of file, iniator file name, and a graph above all of that
- You can filter the types of resources by clicking on the files types above like CSS or JS, or XHR / Fetch / AJAX requests, etc
- `WS` = websocket which pertains to `liveserver` extension
- If you click a file name and then the `Headers` tab you see `Request Method`, `Status Code`, `Response Headers`, ...he said Cookies but I don’t see that
- I tried it on the freeCodeCamp site and none of that was visible but saw a note to hit CTRL+R and then it was there – Cookies show there but not for me if I don’t have any I guess
- `AJAX` request – add a button to the HTML, then `addEventlistener` to the JS – important part is the Response tab to show what the `GET` request returned
- Same for a fetch or other API calls I assume – also shows the load time for the `XHR` or `fetch` request
- The more files and the more code you have, the longer the load time
- Reload your page while on that tab to see the load time

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## APPLICATION TAB

- most common to check local and session storage
- you can also check databases, cookies, and cache
- the main one though is `localStorage` followed by `cookies` and `cache`
- This tab is where you can see what is in the browser storage
- Ways to store data inside of a browser – he shows a Clear Storage button but I don’t see that - there is a button for it – 1) Local Storage, 2) Session storage, 3) Cacke Storage, 4) Application Cache, 5) Back-forward cache, 6) Service Workers, 7) IndexedDB & WebSQL are client-side in-browser databases, 8) Cookies, 9) Trust Tokens, 10) Interest groups and more
- Headings in left pane: Application | Storage | Cache | Background Services | Frames
- Local storage - `localStorage.setItem('name', 'Jim')` then save then reload – then try `console.log(localStorage.getItem('name'))`
- Local storage will stay on your machine until it is cleared which you can clear in your JS file or from the application tab – use `localStorage.clear()`
- Session storage has the same API / syntax except it goes away when the browser is closed
- `Cookies` – you can track cookies – to create a cookie, go into your JS file, use `document.cookie = "username=Jim Kernix";` - it won’t have an `Expires/Max-Age` set so it ends when the session end but you can set an expiration – you can clear it out the same way as for session or local storage
- Click on the `Storage` text in the left pane and click the `Clear site data` button to clear everything that is checked below

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## TIMELINE TAB

> There is no Timeline tab. I think these notes should be listed as a pane under another tab, maybe Performance.

- Use when you have performance issues - it records the performance and you can then look at the details -
- click the record btn > then refresh the page > wait then click Stop
- it captures stacks, JS profiles, memory, and paint -
- in the top pane you can zoom in on details, you can check the summary
- there are color coded bars for different aspects - you can switch views -
- the Summary tab at the bottom gives details on anything you click -

## SECURITY TAB

- you can see `Connection`, `Certificate`, `Certificate Transparency`
- that's about it

## MEMORY TAB

- You can check how much memory JS objects are storing
- This is for advanced level checking of your page
- use with memory problems - there is a lot of info
- she called it the Profiles tab (?)
- shows the execution time and memory usage of your page/app
- Heap snapshot is how the memory is distributed thru your JS objects and DOM nodes
- it will help you with _memory leaks_
- you can choose Summary, Containment, and Statistics views

> ...way too much information!!!

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## LIGHTHOUSE TAB

- select the categories you want to check - check them all - click Generate report
- **_NOTE_**: You can check `localhost` sites!
- Make sure to run the report in incognito mode to remove influences from cached files
- This is a huge topic and you have to go thru each error/suggestion one-by-one to try and fix/improve them

> The notes below here were under the category AUDITS TAB but that is from an older video and I believe these should be under LIGHTHOUSE

- takes a picture of the page when it runs -
- it then shows areas for improvement -
- just because a suggestion is there doesn't mean you have to do it
- Remove unused CSS - compare to the command `showCoverage`
- Lighthouse: it’s not called Audits but Lighthouse now – gives ratings based on the performance of the website, gives suggestions to make it perform better
- You also need to take into account the server you are on – so is it a shared hosting acct or other – he chose everything except Progressive Web App
- Click `Run Audit` – shows page spped, first contentful paint, performance, accessibility, best practices, SEO, time to interactive, total blocking time
- It shows Opportunities to make improvements, Diagnostics, Passed Audits, ARIA,

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>
