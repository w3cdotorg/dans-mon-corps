# Dans mon corps 🔎

Un petit explorateur du corps humain pour les enfants (dès 4 ans), en français.
Une page web unique, sans dépendance ni installation : on ouvre `index.html` et c'est parti.

Inspiré de l'ambiance de [*Corpus*](https://www.reseau-canope.fr/corpus/) (Réseau Canopé) —
corps lumineux au centre, fond de planétarium, une couche par système — mais simplifié et
sonorisé pour des enfants qui ne lisent pas encore.

## Ce que ça fait

- **Un gros curseur** traverse cinq couches en fondu continu : la peau → les os → les muscles
  → le sang → les organes. Cinq pastilles illustrées font la même chose d'un seul appui, et
  les flèches du clavier aussi.
- **Chaque partie du corps est cliquable** : une étiquette apparaît, une explication de deux
  phrases s'affiche, et **tout est lu à voix haute en français** (synthèse vocale du
  navigateur) — essentiel pour un enfant qui ne lit pas. 52 structures nommées.
- **Une loupe** avec déplacement au doigt, pour aller regarder le crâne, la main ou les
  intestins de près.
- **Un mini-jeu** « Trouve la bonne partie ! » en trois questions, avec confettis et étoiles.
- **Un bouton « Montrer les zones »** qui fait pulser tous les endroits où l'on peut appuyer
  (indispensable sur tablette, où il n'y a pas de survol).
- **Garçon ou fille**, cinq carnations et six couleurs de cheveux.
- Animations d'ambiance : clignement des yeux, respiration des poumons, cœur qui bat, sang
  qui circule (sens centrifuge dans les artères, centripète dans les veines).

## L'anatomie est prise au sérieux

Les quatre planches internes ne sont pas des schémas symboliques :

| Couche | Contenu |
|---|---|
| **Os** | Les 12 paires de côtes avec leur obliquité, 7 paires de cartilages costaux, 3 fausses côtes et 2 flottantes, sternum en 3 parties, 7 cervicales + 12 thoraciques + 5 lombaires, sacrum, clavicules en S, omoplates, radius **et** ulna, 8 os du carpe, 3 phalanges par doigt et 2 au pouce, bassin et trous obturateurs, fémur/rotule/tibia/fibula, 20 dents de lait |
| **Muscles** | Deltoïde, grand pectoral en éventail, grand droit avec ligne blanche et 3 intersections tendineuses, obliques, dentelé antérieur, biceps/triceps/brachial, brachio-radial, quadriceps en 3 faisceaux, sartorius, gastrocnémien, tibial antérieur, tendons |
| **Sang** | Cœur anatomique et ses coronaires, crosse aortique, carotides, sous-clavières, veines caves, petite circulation (artère pulmonaire en bleu, veines pulmonaires en rouge), réseau jusqu'aux arcades palmaires et aux orteils |
| **Organes** | Cerveau à circonvolutions et lobes, cervelet, moelle épinière, trachée annelée, poumon droit à 3 lobes / gauche à 2 avec incisure cardiaque, diaphragme, tube digestif complet, reins (le droit plus bas), uretères, vessie, thyroïde |

La latéralité de la vue de face est respectée : foie à gauche de l'image, estomac et rate à
droite, pointe du cœur vers la droite de l'image.

## Utilisation

```bash
open index.html          # macOS
```

Pour y accéder depuis une tablette ou un autre poste du réseau local :

```bash
python3 -m http.server 8000 --bind 0.0.0.0
# puis http://<ip-de-la-machine>:8000/index.html
```

## Technique

Un seul fichier : HTML, CSS et JavaScript en ligne, dessin en SVG écrit à la main
(≈ 880 éléments, `viewBox="0 0 400 820"`). Aucune bibliothèque, aucune image bitmap, aucun
appel réseau. Les membres et organes pairs sont dessinés une fois puis reflétés
(`<use transform="translate(400 0) scale(-1 1)">`). Les deux polices viennent de Google Fonts
avec repli sur des polices système, donc la page reste correcte hors ligne.
`prefers-reduced-motion` coupe les animations.

## Licence

MIT.
