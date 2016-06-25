# light-css
A simple CSS framework with just the strictly necessary (grid, reset, flexbox)


--------------------

DOCUMENTATION (only available in french for the moment)

--------------------

/******

ENCORE UN FRAMEWORK CSS ?

******/

Oui, mais ultra léger et ultra facile à prendre en main.

A quoi ça sert ?

-   reset.css pour un css clean sur tout navigateur
-   base bootstrap pour la grille avec ajout d'une définition xxs en plus de xs sm md lg ->
-   initiation aux bonnes pratiques : la taille du texte est fixée selon celle du navigateur client (normalement 10px)
    fixer font-size pour chaque élément désiré grâce à la nouvelle unité "rem" ou 1 rem = 10px et 1.8 rem = 18px (en théorie, la force de l'unité est qu'elle s'adapte au client)
    line-height à fixer soi-même selon la police (au moins sur les div et les p) à environ 170%
    bannir le pixel
-   qqs classes utiles et un code propre facilement personnalisable
-   utilisation des dernières technologies CSS3 : flexbox, box-sizing, rem, etc...

/!\ ASTUCE /!\
La propriété box-sizing est appliquée à TOUS les éléments
Conséquence : si vous appliquez une border ou un padding à un élément, ça ne change plus sa taille
Par exemple vous avez 4 éléments alignés avec 25% de width et une border de 5px
Normalement le 4ième élément et renvoyé à la ligne, hé bien là tout s'ajuste parfaitement ;)

/******

LES CLASSES

******/

.container (largeur fixe prédéfinie qui s'adapte à la largeur de l'écran / exemple : écran de + de 1200px largeur à 1170px)
.container-fluid (largeur 100%)

-> englobe un ensemble de lignes (rows)

.row

-> englobe un ensemble d'item (items)
-> peut s'étaler sur plusieurs lignes en fonction du nb d'items

.item

-> possède une largeur en pourcentage selon la taille de l'écran et le nombre de colonne voulue dans la ligne
-> voir doc bootstrap
-> largeur d'écran dispo xxs xs sm md lg (on commence toujours par fixer la taille xxs puis on regarde si des classes de taille plus grand existent)
-> de 1 à 12 colonnes

.item-content

-> parfois il sera intéressant de mettre un item avec une image de fond / couleur et un texte avec padding
-> et que le tout soit aligné avec la grille
-> pour cela placer un .item-content et ajoutez lui un fond et du contenu

.square + .square-content

-> si vous avez besoin de rendre une div facilement responsive appliquez lui cette classe
-> puis si vous voulez ajouter du contenu ajouter une classe à l'intérieur de .square s'appelant .square-content
-> attention mettre une div en square c'est bloquer sa hauteur, veillez donc à ce que votre texte ne dépasse pas

.txt-center, .txt-left, .txt-right

-> quelques classes pour appliquer rapidement un text-align à un élément

a

-> on enlève simplement le soulignement et la couleur bleu

.flex .center

-> envie de centrer parfaitement un élément dans une div (à la fois horizontalement et verticalement) ?
-> appliquez la classe .flex à cette div puis .center à l'élément et le tour est joué

/******

EXEMPLE DE STRUCTURE

******/

.container
    .row
        .item .col-xxs-12 .col-xs-3
        .item .col-xxs-12 .col-xs-3
        .item .col-xxs-12 .col-xs-3
        .item .col-xxs-12 .col-xs-3
    /row
    .row
        .item .col-xxs-12
            .item-content
    /row
    .row
        .item .col-xxs-12 .col-xs-4
            .square
                .square-content
        .item .col-xxs-12 .col-xs-4
                    .square
                        .square-content
        .item .col-xxs-12 .col-xs-4
                    .square
                        .square-content
    /row
/container