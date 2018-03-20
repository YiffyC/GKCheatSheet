## Semaine Projet

------

[TOC]

------

##### Le Schéma du récap

![](/Users/Berenger/Documents/GitKraken/GKCheatSheet/images/20180319-SchemaRecap.png)

------

##### Stratégies JPA

—> Single table strategy - Arborécenvce traduit en une seule table. Hibernate utilise des valeurs de discrimination pour faire la selection de table

```java
@discriminationColumn("type")
@discriminationValue("Vh")
```

| Vehicule | Type |
| -------- | ---- |
| xxxxx    | Vh   |
| xxxx     | Vh   |
| xxxx     | c    |

—> Join : Pour récupérer les camions, sous type de véhicule:

```Java
@join("Véhicule")
@join("Camion")
```

