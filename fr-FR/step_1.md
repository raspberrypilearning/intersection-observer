`IntersectionObserver` est utilisé pour détecter quand un élément (par exemple `<img>`, `<p>` ou `<div>`) entre ou quitte la fenêtre du navigateur de l'utilisateur.

It is commonly used to 'lazy load' images and trigger animations.

L'observateur comporte trois parties principales :

**Éléments cibles :** tu spécifies quels éléments tu veux que l'observateur obtienne. Ce sont les éléments qui t'intéressent pour savoir s'ils sont entrés ou non dans la fenêtre d'affichage.

**Callback:** The callback is a function that is triggered when the observed element enters or exits the viewport. The function could output a messange to the Console, or change an HTML element, for example.

**Options:** You can also provide some options to the intersection observer, like setting a threshold. The threshold is the amount of the observed element that needs to be visible to trigger the callback. Par exemple, tu peux utiliser un seuil de 0,5 pour être averti lorsqu'un élément est visible à 50 %, ou un seuil de 1 pour être averti lorsqu'un élément est entièrement visible.

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
console.log("BOUNCE TRIGGER DANS LA FENÊTRE D'AFFICHAGE");
}
});
bounceObserver.observe(document.querySelector("#hideBounce"));

\--- /code ---

On line 1, `entries` is a collection of all elements on the webpage with the `id="hideBounce"` attribute. Ce sont les éléments cibles, comme indiqué dans l'appel de l'observateur à la ligne 6.

Une collection d'éléments est appelée un « tableau ».

The `bounceObserver` is set to observe when the first (in this case, the only) item in the `entries` array comes into the viewport (using `isIntersecting` on line 2).

Lorsqu'il le fait, l'observateur 'callback' envoie un message à la console (ligne 3).
