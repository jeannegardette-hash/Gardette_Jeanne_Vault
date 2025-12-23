## démarche suivie

### Choix de la source

Pour commencer, j’ai choisi une page Wikipédia comme source principale.  
Ce choix s’explique par le fait que Wikipédia contient beaucoup d’informations structurées (dates de sortie, synopsis, équipe du film) et que le code HTML est relativement lisible, ce qui facilite le scraping. 
[lien wikipédia]("https://fr.wikipedia.org/wiki/Toy_Story")

---

### Outils utilisés

Le scraping a été réalisé avec **R**, en utilisant des plugins dédiés au web scraping, notamment **rvest**.  
Ces outils permettent de récupérer automatiquement le contenu d’une page web sans avoir à copier les informations manuellement.
![[installation library.png]]
---

### Récupération de la page

La première étape technique consiste à charger le code HTML de la page grâce à la fonction :

`read_html(url)`

Cette fonction permet d’importer la page Wikipédia dans R afin de pouvoir analyser sa structure.

---

### Sélection des informations

Une fois la page chargée, j’ai sélectionné uniquement les parties qui m’intéressaient (par exemple la date de sortie ou le résumé).  
Pour cela, j’ai utilisé des **sélecteurs CSS**, comme :

- `.infobox` pour les informations générales du film
    
- `#Synopsis + p` pour récupérer le paragraphe du résumé
    

La fonction utilisée est :

`html_nodes()`

Elle permet de cibler précisément des éléments dans le code HTML.

---

### Extraction du texte

Après avoir sélectionné les bons éléments, j’ai extrait uniquement le texte avec :

`html_text()`

Cette étape permet de supprimer le code HTML et de garder uniquement les données utiles.

---
![[code.png]]