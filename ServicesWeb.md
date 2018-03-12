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

------

##### <u>Services web</u> 

Sont basés sur les langages et protocoles web HTTP, XML, TCP/IP qui ne nécéssitent pas de configuration particulière. Ils possèdent un contrat de fonctionnement qui content les informations nécessaires à leuur fonctionnement.

------

##### <u>Technos disponibles</u>

- Webservices étendus : s'appuient sur les standards UDDI/WSDL(fichier XML de definition de service)/SOAP
- Webservices REST (Representationnal State Transfer) : Utilise dirrectement HTTP au lieu de passer par SOAP. Utilise URI pour nommer et identifier une ressource. 

------

##### <u>Services web REST</u>

Exploités pour les architectures orientées données (DOA). Rest n'est pas un standard. REST est un style d'architecture basé sur un mode de compréhension du web. Rest s'appuie sur les standards du web : 

- Protocole HTTP
- URLs
- Formats de fichiers
- Sécurité via SSL

