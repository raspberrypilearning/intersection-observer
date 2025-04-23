De `IntersectionObserver` wordt gebruikt om te detecteren wanneer een element (bijv. `<img>`, `<p>` of `<div>`) de browserviewport van de gebruiker binnenkomt of verlaat.

Het wordt vaak gebruikt voor het vertraagd laden van afbeeldingen en het activeren van animaties.

De observator bestaat uit drie hoofdonderdelen:

**Target (Doel) elementen:** Je specificeert welke elementen je wilt laten waarnemen door de observator. Dit zijn de elementen waarvan je wil weten of ze de viewport zijn binnengekomen of verlaten.

**Callback:** De callback is een functie die wordt geactiveerd als het waargenomen element de viewport binnenkomt of verlaat. De functie kan bijvoorbeeld een bericht naar de console sturen of een HTML-element wijzigen.

**Options (Opties):** Je kunt ook enkele opties voor de intersection observator aanbieden, zoals het instellen van een threshold (drempelwaarde). De drempelwaarde is de hoeveelheid van het waargenomen element die zichtbaar moet zijn om de callback te activeren. Je kunt bijvoorbeeld een drempelwaarde van 0.5 gebruiken om een melding te ontvangen wanneer een element voor 50% zichtbaar is, of een drempelwaarde van 1 om een melding te ontvangen wanneer een element volledig zichtbaar is.

Hier is een voorbeeld van het gebruik van `IntersectionObserver` uit het project [Geanimeerd verhaal](https://projects.raspberrypi.org/nl-NL/projects/animated-story) in het pad [Meer web](https://projects.raspberrypi.org/nl-NL/raspberrypi/more-web):

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
bounceObserver.observe(document.querySelector("#hideBounce"));

--- /code ---

Op regel 1 is `entries` een verzameling van alle elementen op de webpagina met het kenmerk `id="hideBounce"`. Dit zijn de doelelementen, zoals gespecificeerd in de observer-aanroep op regel 6.

Een verzameling items wordt een 'array' genoemd.

De `bounceObserver` is ingesteld om te observeren wanneer het eerste (in dit geval: het enige) item in de `entries`-array in de viewport verschijnt (met behulp van `isIntersecting` op regel 2).

Wanneer dit het geval is, stuurt de observator 'callback' een bericht naar de Console (regel 3).