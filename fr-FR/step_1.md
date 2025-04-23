`IntersectionObserver` est utilisé pour détecter quand un élément (par exemple `<img>`, `<p>` ou `<div>`) entre ou quitte la fenêtre du navigateur de l'utilisateur.

Il est couramment utilisé pour charger des images à chargement lent et déclencher des animations.

L'observateur comporte trois parties principales :

**Éléments cibles :** tu spécifies quels éléments tu veux que l'observateur obtienne. Ce sont les éléments qui t'intéressent pour savoir s'ils sont entrés ou non dans la fenêtre d'affichage.

**Callback :** la fonction callback (rappel) est une fonction qui est déclenchée si l'élément observé entre ou quitte la fenêtre d'affichage. Cela pourrait être une sortie vers la Console, ou un changement vers un élément HTML, par exemple.

**Options :** tu peux également fournir quelques options à l'Intersection Observer, comme définir un threshold (seuil). Le seuil est un pourcentage de la visibilité de l'élément observé nécessaire pour déclencher le callback. Par exemple, tu peux utiliser un seuil de 0,5 pour être averti lorsqu'un élément est visible à 50 %, ou un seuil de 1 pour être averti lorsqu'un élément est entièrement visible.

Voici un exemple d'utilisation d' `IntersectionObserver` du projet [Histoire animée](https://projects.raspberrypi.org/en/projects/animated-story) dans le parcours [Plus de web](https://projects.raspberrypi.org/en/raspberrypi/more-web) :

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

À la ligne 1, `entries` est une collection de tous les éléments de la page web avec l'attribut `id="hideBounce"`. Ce sont les éléments cibles, comme indiqué dans l'appel de l'observateur à la ligne 6.

Une collection d'éléments est appelée un « tableau ».

Le `bounceObserver` est configuré pour observer lorsque le premier (dans ce cas : le seul) élément du tableau `entries` arrive dans la fenêtre d'affichage (en utilisant `isIntersecting` à la ligne 2).

Lorsqu'il le fait, l'observateur 'callback' envoie un message à la console (ligne 3).