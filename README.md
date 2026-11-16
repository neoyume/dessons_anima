# Trait Live

**[Essayer en ligne → neoyume.github.io/dessons_anima](https://neoyume.github.io/dessons_anima/)**

Anime en live sur une vidéo : lance la lecture et dessine au Pencil (ou à la souris). Chaque trait est posé au moment exact où tu le traces, et il revient à chaque replay. Ralentis la vidéo pour tracer plus précisément, mets en pause pour dessiner sur une image précise, et exporte le résultat en vidéo ou en séquence PNG.

Un outil de la famille [Dessons](https://github.com/neoyume/dessons), par [neoyume](https://github.com/neoyume), dont il reprend la direction artistique : palette teal et vert néon, police pixel DotGothic16, palette de couleurs `NY_` et disposition du mode Dessin.

Tout tourne dans le navigateur : aucun serveur, aucune dépendance, la vidéo ne quitte jamais ta machine.

## Utiliser

- **En ligne** : ouvre [la page](https://neoyume.github.io/dessons_anima/), sur ordinateur ou sur iPad.
- **En local** : double-clique sur `index.html`. Ou lance un petit serveur dans le dossier :
  ```bash
  python3 -m http.server 8000
  ```
  puis ouvre `http://localhost:8000`.

Garde le dossier `fonts/` à côté de `index.html` : la police est servie depuis là.

## Fonctionnement

- **Outils** (colonne de gauche) : **Plume**, **Néon** (trait lumineux) et **Gomme**, qui efface les traits visibles à l'image courante.
- **Trait** : taille, opacité, lissage du geste, pression du Pencil.
- **Durée de vie** : combien d'images un trait reste à l'écran après avoir été tracé (de 1 à 96 images), jusqu'à la fin de la vidéo, ou sur toute la vidéo. Options :
  - *Effacement progressif* : la queue du trait disparaît dans l'ordre du tracé, comme un trait qui se dessine et s'efface en même temps ;
  - *Fondu de sortie* : le trait s'estompe sur sa durée ;
  - *Tracé progressif* : au replay, le trait se redessine à la vitesse de ton geste.
- **Couleur** (panneau de droite) : les 36 couleurs `NY_` de Dessons, ou une couleur perso.
- **Affichage** : *Fantômes* montre tous les traits en transparence, pour se repérer dans l'animation ; *Pencil uniquement* réserve les doigts aux gestes.
- **Timeline** : la bande au-dessus de la barre de lecture montre où vit chaque trait. Vitesse de lecture 0,25× à 1×, boucle, cadence (12 à 60 i/s, détectée automatiquement à la première lecture).

Les réglages s'appliquent aux nouveaux traits. Sur grand écran, les réglages du trait sont à gauche de la vidéo et les couleurs à droite ; sur un écran plus étroit, tout passe dans le panneau de droite, qu'on ouvre avec **Réglages**.

### Gestes et raccourcis

| | |
|---|---|
| Tap 1 doigt | lecture / pause |
| Tap 2 doigts | annuler |
| Tap 3 doigts | rétablir |
| Espace | lecture / pause |
| ← → | image précédente / suivante |
| B / N / E | plume / néon / gomme |
| ⌘Z / ⇧⌘Z | annuler / rétablir |

## Enregistrer et exporter

- **Sauvegarde automatique** : les traits sont gardés dans le navigateur pour chaque vidéo. En rouvrant la même vidéo, Trait Live propose de les restaurer.
- **Projet** → *Enregistrer* : un fichier `.json` avec tous les traits, à recharger plus tard sur la même vidéo. Plus sûr que la sauvegarde du navigateur.
- **Exporter** :
  - *Vidéo + dessins* (`.mp4`, ou `.webm` selon le navigateur), avec le son en option ;
  - *Dessins seuls* : une image PNG transparente par frame, dans un `.zip`, pour After Effects, Dreams, etc. ;
  - *Dessins sur fond vert* (`.mp4`), pour une incrustation chroma key. Évite alors la couleur `NY_melonsoda` : c'est le même vert que le fond, elle disparaîtrait à l'incrustation.

Les exports vidéo se font en temps réel : la vidéo est rejouée du début à la fin pendant l'enregistrement, garde l'onglet ouvert.

## Navigateurs

Pensé pour Safari sur iPad avec l'Apple Pencil ; marche aussi dans un navigateur de bureau, à la souris ou à la tablette graphique. Formats vidéo : ceux que lit le navigateur (MP4 / MOV en H.264 partout, WebM sur Chrome et Firefox).

## Licences

La police DotGothic16 est sous [SIL Open Font License](fonts/OFL.txt).
