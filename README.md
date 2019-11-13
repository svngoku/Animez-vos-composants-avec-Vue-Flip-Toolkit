# Vue Flip Toolkit
Enveloppez tous les enfants animés avec un seul composant Flipper doté d'un accessoire `flipKey` qui change à chaque fois qu'une animation doit se produire.

Enveloppez les éléments qui doivent être animés avec des composants Flipped ayant un prop `flipId` les correspondant dans les rendus.

## Details

Flip toolkit est un composant qui permet de créer des animations complexes simplement en traçant la position des différents objects.

Ces deux composants sont `Flipped` et `Flipper`.

* `<Flipper />`: composant utilisés  pour englober toute une série d'élements que l'on souhaite rendre dynamique .

* `Flipped` : permet de désigner un élement qui doit etre animé.

Nous devons toujours penser à mettre des clés qui seront unique pour chaque éléments , au risque d'avoir des problèmes cotés animations. Et penser à bien utiliser la props `shouldFlip` afin d'optimiser les perfermances et de ne pas déclenher des calculs unitilement .


## Ressource

[Article](https://www.grafikart.fr/tutoriels/vue-flip-toolkit-1208)

[Librarie Vue-flip-toolkit](https://github.com/mattrothenberg/vue-flip-toolkit)
