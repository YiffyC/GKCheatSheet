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
- Sans état
- Découvrabilité
- Composabilité



Contrat Standardisé : 

Entre le consommateur et le fournisseur de données. Il est lié à :

- La Syntaxe (*ex: attends un entier*)
- La sémantique (= définition des règles (*ex: Nombre de compte pas négatif*))
- La qualité du service (temps de réponse, tolérence aux pannes)



Couplage faible :

Echange de messages et passage par une interface —> pas d'accès dirrect aux classes métier



Abstraction :

Le contract ne dois contenir que les infos pertinentes. Fonctionne en "boite noire" : le fonctionnement ne dois pas être visible. Pas de variation dans le comportement du service.



Réutilisabilité *(peu utilisé en vrai)* :

Service accessible depuis un annuaire. le fournisseur doit déposer et mettre à jour le service. Utilise les standards (UDDI, ebXML) 



Autonome/sans état :

Sans état : garantie plus de performance. Autonomie = prédicabilité



Composabilité : 

Doit fonctionner de façon modulaire et non pas intégrée. Décompose un système complexe. S'inscrit dans une logique de compsition de services. 