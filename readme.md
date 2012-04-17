Impressive.js
---------------

impressive.js is a fork of impress.js (v0.3) that extends it a little bit to make it easy for a developer to use impress.js to build whole websites and not just presentations.  

All credit goes to Bartek Szopka for his awesome library.
  
Samuel Hough (@samshough) 

-------

impress.js
---
impress.js is a presentation tool based on the power of CSS3 transforms and transitions
in modern browsers and inspired by the idea behind prezi.com.

MIT Licensed.

Copyright 2011-2012 Bartek Szopka (@bartaz)
 
author:  Bartek Szopka
version: 0.3
url:     http://bartaz.github.com/impress.js/
source:  http://github.com/bartaz/impress.js/

-------

IMPRESSIVE.JS
-
example site:
>http://www.julialocascio.com/

DOM Changes:
-
>class="fixture"
> >Elements you want in the slide show follow the same pattern of needing "step" class when you would like for the to be transformed via 3d Transformations and appear in your slideshow. Additionally, you can add the class "fixture" to an element and it will have the same 3d Transformations applied to it, but it will not be possible to navigate to it as part of the slideshow.  Create elements that are there merely for decoration and not part of your actual slideshow.

> Example:
    
    <div class="fixture" data-x="5000" data-z="-1400" data-y="2000" data-rotate-y="0" data-scale="18">
        <video id="lightning-video" class="hide" width="720" height="480" loop>
            <source src="video/littlegirl.ogv" type="video/ogg">
            <source src="video/littlegirl.webm" type="video/webm">
            <source src="video/littlegirl.mp4" type="video/mp4">
        </video>
     </div> 

JS Api
-


> impressive.ifSupport(): 
>> Pass in a function to be executed when impressive.js is supported.  Optionally you can pass in scope to call the function by otherwise it will default to  the window scope

          var runIfSupport = function(){// does stuff i want to do if support is there };
          impressive.ifSupport(runIfSupport);

> impressive.ifNoSupport()
>> Pass in a function to be executed when impressive.js is not supported.  Optionally you can pass in scope to call the function by otherwise it will default to  the window scope

          var runIfNoSupport = function(){// does stuff i want to do if support isn't there :( };
          impressive.ifNoSupport(runIfNoSupport);

> impressive.ifEither()
>> Pass in a function to be executed when impressive.js in either case.  Optionally you can pass in scope to call the function by otherwise it will default to  the window scope

          var runIfEither = function(){// does stuff i want to do if support isn't there :( };
          impressive.ifNoSupport(runIfEither);


> impressive.addElement()
>>Pass in a DOM element or id of a DOM element with the proper data attributes to have it added to the slideshow dynamically after the impressive has run.

          <div id='newDiv' data-x="5000" data-z="-1400" > something pretty </div>
          ....
          <script>
          impressive.addElement('newDiv');



> impressive.forceSupport()
>> Drops a cookie on the users browser to force the browser to run as though it has support on the next page load.  Will ignore whether the browser actually has support or not.  Allows switching between CSS3d version and non CSS3d version
          
          impressive.forceSupport();

> impressive.forceNoSupport()
>> Drops a cookie on the users browser to force the browser to run as though it has support on the next page load.  Will ignore whether the browser actually has support or not.  Allows switching between CSS3d version and non CSS3d version

          impressive.forceNoSupport();

> impressive.onActive()
>> Pass in a function to be called when a new element is the active element on the page.  Receives in order the active dom element, next dom element in the slideshow, and the previous dom element in the slideshow.
          
          var activeElementHandler = function(active, nextElement, previousElement){
                    // Do stuff with these three elements
          };
          impressive.onActive(activeElementHandler);

> impressive.init()
>> Starts impressive.js.  Call after you have set up your slideshow and passed in all of the functions you want run when there is support or no support.

          impressive.init