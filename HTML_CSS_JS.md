## HTML, CSS, JavaScript

------

[TOC]

------

#### HTML

##### Balises

```Html
<html> </html>
```



------

##### Paramètres

La balise img prends un paramètre src :

```html
<img src="url" />
```

------

##### Titre de la page

```html
<title>Titre</title>
```

------

##### Titres au sein de la page

```html
<h1>Titre 1</h1>
<h6>Titre 6</h6>
```

------

Listes

```Html
<!-- Ordonnée -->
<ol>
    <li></li>
</ol>

<!-- Non ordonnée -->
<ul>
    <li></li>
</ul>

<!-- de definition -->
<dl>
    <dt>
    	<dd></dd>
	</dt>
</dl>
```

------

##### Liens

```html
<a href="destination">Texte du lien</a>
```

Ancre:

```html
<a id="ancre">texte</a>
<a href"#ancre">texte2</a>
```

------

##### Image

```Html
<img src="adress" alt="description alternative" />
```

------

##### Organisation

```html
<div> Bloc</div>

<span>Ligne </span>
```

------

##### Inclure du CSS

```html
<link rel="stylesheet" type="text/css" href="chemin/style.css" />
```

------

Formulaires

```Html
	  <form method="post">
		  <input type="text" />Nom<br />
		  <input type="date" />Date de naissance<br />
		  <p>Meilleur navigateur?</p>
		  <group>
		  	<input name="btn" type="radio" />Firefox<br />
			<input name="btn" type="radio" />Chrome<br />
			<input name="btn" type="checkbox" />Safari<br />
			<input name="btn" type="checkbox" />IE<br />
		  </group>		  
		  <input type="submit" />	  
	  </form>
```



------



#### CSS

##### Notations

```css
h1
{
    /*Traitement sur toutes les balises h1 du document*/
}

.nomClasse
{
    /*Traitement appliqué à toutes les balises contenant l'attribut class="nomClass" */
}

#nomId
{
    /*Traitement appliqué à l'élément ayant pour attribut id="nomid" */
}
```

