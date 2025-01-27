# Manipulation interactive des graphes avec Sage
Le logiciel SageMath, est un logiciel connu libre et open-source de calcul mathématiques très populaire auprès des scientifiques. Il contient une grande partie implémentée concernant les graphes et leurs algorithmes (le backend programmé en Python). En revanche le frontend est actuellement assez limité et l'utilisateur doit presque entièrement passer par la ligne de commandes. On peut visualiser les graphes en différents formats, et notamment sur un navigateur sous forme d'objets graphiques avec la librairie Javascript d3js, mais on ne peut pas les manipuler "à la main". L'an dernier une équipe d'étudiants de l'IUT avait produit une solution pour résoudre ce problème et permettre une manipulation interactive des graphes à travers un navigateur. Leur solution est ici : https://github.com/NaokimTheFirst/JS_Graph_Sage 

Le but du projet est de terminer le travail en enrichissant cette solution. Il s'agit d'ajouter des nouvelles fonctionnalités interactives de manipulations des dessins et les intégrer au projet SageMath. Une possibilité serait de programmer des déroulements d'algos de Sage existants sur un navigateur. Technos : Python (avec SageMath), Javascript, Git.

### Tuteur : Valicov

#### 24/01/2022 - 2e rdv avec tuteur
- Creation d'un fork : https://github.com/Dalwaj/JS_Graph_Sage
- Pull des modifications pour 'attach' par Jawad
- A faire : Diagramme de classes (+ sequences), ajouter les fonctionnalités à l'interface graphique (afficher nombre de sommets, déplacer la partie du graph sélectionnée...)

#### 03/02/2022 - 3e rdv avec tuteur
*Problèmes à resoudre :* 
- animation du drag d'une multiselection (à voir si c'est lié au renouvellement trop rapide du fenêtre),
- perte de connexion lors de renouvellement du fenetre, 
- absense de connexion inverse entre SageMath et JS_Graph,
- les types des sommets sont transformés en string lors de la connexion.

*Solution proposée pour le problème des strings :* créer un dictionnaire (une map) qui associe à chaque sommet v du graphe initial une chaîne de caractères cv qui est sa représentation textuelle que vous allez utiliser dans le format JSON. Toutes les opération que vous allez effectuer dans d3js sur cv seront transposé sur v à travers ce dictionnaire.