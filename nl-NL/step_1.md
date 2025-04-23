De `IntersectionObserver` wordt gebruikt om te detecteren wanneer een element (bijv. `<img>`, `<p>` of `<div>`) de browserviewport van de gebruiker binnenkomt of verlaat.

It is commonly used to 'lazy load' images and trigger animations.

De observator bestaat uit drie hoofdonderdelen:

**Target (Doel) elementen:** Je specificeert welke elementen je wilt laten waarnemen door de observator. Dit zijn de elementen waarvan je wil weten of ze de viewport zijn binnengekomen of verlaten.

**Callback:** The callback is a function that is triggered when the observed element enters or exits the viewport. The function could output a messange to the Console, or change an HTML element, for example.

**Options:** You can also provide some options to the intersection observer, like setting a threshold. The threshold is the amount of the observed element that needs to be visible to trigger the callback. Je kunt bijvoorbeeld een drempelwaarde van 0,5 gebruiken om een melding te ontvangen wanneer een element voor 50% zichtbaar is, of een drempelwaarde van 1 om een melding te ontvangen wanneer een element volledig zichtbaar is.

Here is an example of the use of `IntersectionObserver` from the [Animated story](https://projects.raspberrypi.org/en/projects/animated-story) project in the [More web](https://projects.raspberrypi.org/en/raspberrypi/more-web) path:

## --- code ---

language: js
filename:
line_numbers: true
line_number_start: 1
line_highlights:
-----------------------------------------------------

const bounceObserver = new IntersectionObserver((entries) => {
if (entries[0].isIntersecting) {
console.log("STUITER TRIGGER IN VIEWPORT");
}
});
bounceObserver.observe(document.querySelector("#hideBounce"));

\--- /code ---

On line 1, `entries` is a collection of all elements on the webpage with the `id="hideBounce"` attribute. Dit zijn de doelelementen, zoals gespecificeerd in de observer-aanroep op regel 6.

Een verzameling items wordt een 'array' genoemd.

The `bounceObserver` is set to observe when the first (in this case, the only) item in the `entries` array comes into the viewport (using `isIntersecting` on line 2).

Wanneer dit het geval is, stuurt de observer 'callback' een bericht naar de Console (regel 3).
