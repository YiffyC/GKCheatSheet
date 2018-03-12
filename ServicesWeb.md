## Service Web Java

------

[TOC]

------

##### <u>Architecture SOA</u> (Service Oriented Architecture)

- Collaboration pour des tâches communes
- Distants géographiquement mais interconnectés
- Hétérogène

------

##### <u>Service</u>

Un service est un composant logiciel *distribué*, exposant les fonctionnalités à forte valeur ajoutée d'un dommaine métier. Le service peut être carractérisé par 8 aspects:

- Contrat standardisé
- Couplage faible
- Abstraction
- Réutilisabilité
- Autonomie
- <u>Sans état (= pas de session *(Ex: pas de panier comem sur site de commerce)*)</u>
- Découvrabilité
- Composabilité



Contrat Standardisé: Entre le consommateur et le fournisseur de données. Il est lié à :

- La Syntaxe (*ex: attends un entier*)
- La sémantique (= définition des règles (*ex: Nombre de compte pas négatif*))
- La qualité du service (temps de réponse, tolérence aux pannes)



Couplage faible :

Echange de messages et passage par une interface —> pas d'accès dirrect aux classes métier



Abstraction:

Le contract ne dois contenir que les infos pertinentes. Fonctionne en "boite noire" : le fonctionnement ne dois pas être visible. Pas de variation dans le comportement du service.



Réutilisabilité:

