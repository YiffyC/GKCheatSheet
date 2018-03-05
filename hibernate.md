## Hibernate - persistence



[TOC]



------

##### <u>Sérialisation</u>

Sauvegarde de l'état d'un objet sous forme d'octets.

------

##### <u>ORM</u>

Object Relational Mapping. permet de mapper des objets avec des tables.

------

##### <u>JPA</u>

Java Percistance API. Norme = JPA 2 : propose un modèle standard de persistance à l'aide d'Entity beans.

------

##### <u>Initialisation de SessionsFactory</u>

```java
private static Configuration configuration;
private static SessionFactory sessionFactory;
private Session s;

try
{
    //etape 1
    configuration = new Configuration();
    
    //etape 2
    sessionFactory = configuration.configure().buildSessionFactory();
    
    //etape 3
    s = sessionFactory.openSession();
}
catch(Throwable ex)
{
    log.error("Building SessionFactory has failed.", ex);
    throw new ExceptionInInitializerError(ex);
}
```

------

##### <u>Entitée</u>

Classe dont les instances peuvent être persistante. (Spécificité de JPA). 

```java
//import
import javax.persistance.Entity;

//use
@Entity
```



Exemple:

```Java
@Entity
public class Book
{
    @Id @GeneratedValue
    private Long id;
    
    @Column (nullable = false)
    private String title;
    private Float price;
    
    @Column (length = 2000)
    private String description;
    private String isbn;
    private Integer nbOfPage;
}
```

------

##### <u>Gestion de la percistance pour hibernate</u>

1. Création & ouverture d'une session hibernate
2. [Debut transaction] - Fortement conseillé
3. Appliquer les opérations de Session pour interagir avec l'environement de persistance
4. [valider ( commit() ) la transaction]
5. Synchroniser avec la base de données (flush) et fermer la session

------

