Day01: DrumKit -
thoughts -
where is he coming up w/ all this stuff you can do in the browser - it's not intuitive for me, I need some docs
addEventListner: https://www.w3schools.com/jsref/met_document_addeventlistener.asp or https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener
querySelector: https://www.w3schools.com/jsref/met_document_queryselector.asp or https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector
querySelectorAll: https://www.w3schools.com/jsref/met_document_queryselectorall.asp
play:
https://www.w3schools.com/jsref/dom_obj_audio.asp <- HTML object docs
https://www.w3schools.com/jsref/met_audio_play.asp <- play() function (or https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
https://www.w3schools.com/jsref/event_onplay.asp <- onPlay event
JS pseudocode:
1. find all of the elements with a class "key" and add an eventlistner for 'transitionend' at which you should call the removeTransition function
2. add an event listener to the window, calling the playSound function when 'keydown' happens
3. when keydown happens:
    1. find the audio element that matches the keyCode that was depressed
    2. find the key that matches the keyCode that was depressed
    3. if not audio element matches then do nothing
    4. for the audio element, rewind the file and play it
    5. when done, add the 'playing' class to the element assigned to key
4. when transitionend happens
    1. do nothing if the property isn't 'transform'
    2. remove the 'playing' class from the element that had the transitionend event
Events:
How do I trigger/listen to an event and what do I get when it triggers?
* Events are triggered when things happen in the DOM - that's the browser's job
* These events only do things if they have listeners - you can add your own listeners to the JS code using the addEventListner function (or something else like it) and give it a callback function to call when the event is triggered
* When your event is triggered and your function is called, the listener sends the event object as an argument to the callback function
* You can find what the EventObject contains by looking first at the Event and determining what type it is (ex: keydown is a KeyboardEvent) - then look up the docs for that EventObject (KeyboardEvent in our case: https://www.w3schools.com/jsref/obj_keyboardevent.asp)
the kbd element:
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/kbd
css transition property:
https://developer.mozilla.org/en-US/docs/Web/CSS/transition
css transform property:
https://developer.mozilla.org/en-US/docs/Web/CSS/transform
