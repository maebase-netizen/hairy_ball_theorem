# Pentina l’eriçó

Un joc per intentar pentinar una esfera peluda sense deixar cap remolí. No es pot fer, i ho diu el teorema de la bola peluda, que Henri Poincaré va demostrar el 1885.

Pàgina: https://maebase-netizen.github.io/hairy_ball_theorem/

La pàgina acompanya l’article [«La bola que et pren el pèl»](https://crmatematica.wordpress.com/2026/07/09/la-bola-que-et-pren-el-pel/), publicat a *El Gegant del π*, el blog de divulgació del Centre de Recerca Matemàtica.

## Contingut del repositori

`index.html` conté la pàgina sencera: HTML, estils i JavaScript. Els gràfics en 3D els fa [three.js](https://threejs.org/) (versió r128, llicència MIT), que és a `vendor/three.min.js` perquè la pàgina no depengui de cap servidor extern. La carpeta `img/` guarda la imatge que fan servir les xarxes socials quan algú comparteix l’enllaç.

## Com es compten els remolins

El pèl viu sobre una icosfera, una esfera feta de triangles (5.120 al mòbil i 20.480 a l’ordinador). Per a cada aresta, el joc calcula quant gira el pèl d’un extrem a l’altre, transportant-lo pel cercle màxim que les uneix. Cada triangle suma els girs de les seves tres arestes, i el nombre de voltes senceres és el seu índex. Com que cada aresta compta amb signe contrari als dos triangles que la comparteixen, la suma de tots els índexs dona exactament 2, la característica d’Euler de l’esfera, per salvatge que sigui el pentinat. Els triangles amb índex que són a prop s’agrupen en un sol remolí.
