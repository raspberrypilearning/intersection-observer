The Intersection observer is used to detect when an element (e.g. `<img>`, `<p>`, or `<div>`) enters or leaves the user's browser viewport.

It is commonly used for lazy loading images, and triggering animations.

Here's how it works:

**Callback:** An observer specifies a callback function. This function is triggered if the observed element enters or exits the viewport.

**Target elements:** You specify which elements you want the observer to observe. These are the elements you're interested in knowing if they enter of exit the viewport.

**Options:** You can also provide some options to the Intersection Observer, like setting a threshold. The threshold is a percentage of the observed element's visibility needed to trigger the callback. For example, you could use a threshold of 0.5 to be notified when an element is 50% visible, or  a threshold of 1 to be notified when an element is fully visible.


Here is an example of the use of `intersection observer` from the [Animated story](https://projects.raspberrypi.org/en/projects/animated-story) project in the [More Web](https://projects.raspberrypi.org/en/raspberrypi/more-web) path:

--- code ---
---
language: js
filename:
line_numbers: true
line_number_start: 1
line_highlights: 
---

const bounceObserver = new IntersectionObserver((entries) => {
  if (entries[0].isIntersecting) {
    console.log("BOUNCE TRIGGER IN VIEWPORT");
  }
});
bounceObserver.observe(document.getElementById("hideBounce"));

--- /code ---

On line 1, `entries` is a collection of all elements on the web page with the `id="hideBounce"` attribute (as specified in the observer call on line 6). 

A collection of items is called an 'array'.

The `bounceObserver` is set to observe when the first (in this case: the only) item in the `entries` array comes into the viewport (using `isIntersecting` on line 2).

When it does, the observer 'callback' outputs a message to the Console (line 3).