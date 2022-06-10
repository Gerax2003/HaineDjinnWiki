# LOAD et SAVE du XML
Présentation de feature

Bonjour, le document suivant a pour objectif d’expliquer comment notre scène est sauvegardée, et comment elle est chargée. Feature présente dans les fichier Engine/GameDefinitions.cpp et .h

## Sauvegarde Dans Le XML:
Pour commencer on vient récupérer notre fichier XML et on l’ouvre dans l’emplacement de notre Scène actuelle, emplacement range grâce à des balises nommées via le nom de la scène.

Ensuite, on ouvre les balises des différentes catégories d'éléments (Objets, Caméras), et on les réécrit en effaçant ce qui était écrit au préalable.

Pour les objets, compte tenu du fait qu'ils sont construits à base de component, on doit aussi les stocker de manière ordonnée, chose faite à l'aide d’autres balises dans la fonction FillDataObject. Puis une fois que toutes nos informations on était remplie, on referme le XML.

## Chargement Du XML:
Pour charger le XML, on refait la même mécanique d’ouverture des balises, sauf que cette fois on récupère les informations qu’elles contiennent depuis les fonctions ExtracInfo respectives à chaque type d‘objet.
