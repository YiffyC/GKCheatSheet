## Java Spring

------

[TOC]

------

##### <u>Introduction</u>

Exigences du projet informatique :

- Performance
- Maintenance
- Sécurité
- Portabilité
- Distribution
- Capacité à communiquer avec d'autres applications distantes
- Capacité de fournir le service à différents types de clients (desktop, mobile, sms, HTTP...)
- Coût du soft

------

##### <u>Definition</u>

<u>Spring</u> :  Framework pour l'inversion de contrôle. Spring est un conteneur léger.

<u>Framework</u> : Cadre de développement. Il contient des bonnes pratiques de développement. Il permet d'éviter de recoder des classes utilitaires. Il fournit le socle technique pour que les développeurs puissent se consentrer sur le code métier.

------

##### <u>Rappels de conception</u>

- Peu de couplage de classe
- Appli fermée à la modification mais ouverte aux changements
- Programmer interface et non une implémentation
- Appli qui n'évolue pas : meurt

------

##### <u>Couplage fort</u>

Quand la classe A est liée à la classe B, on dit que la classe A est fortement couplée à la classe B. A ne peut fonctionner qu'en présence de B. Si une nouvelle classe B2 est créée, on est obligé de modifier dans la classe A.![forte](/Users/Berenger/Documents/GitKraken/GKCheatSheet/images/forte.png)

Le couplage fort est une mauvais pratique. 

------

##### <u>Couplage faible</u>

Pour utiliser le couplage faible, il faut utiliser les interfaces. Classe A utilise une interface IA et la classe B inplémente une interface IB. Si A est lié à l'interface IB par une association, on dit que A et la classe B sont liés par un couplage faible. Dans ce cas, B peut fonctionner avec n'importe quelle classe qui implémente l'interface IA.

------

##### <u>Formes d'injection des dépendances</u>

```Java
import metier.MetierImpl;
import dao.DaoImpl
public class presentation
{
    public static void main (String args[])
    {
        DaoImpl dao = new DaoImpl();
        MetierImpl metier = new Metier();
        metier.setDao(dao);
        System.out.println(metier.calcul());
    }
}
```

