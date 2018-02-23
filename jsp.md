## JSP - Java Server Page



[TOC]



------

##### <u>Résumé</u>

- Composant java
- Executé côté serveur
- Nécessite un serveur qui implémente le composant
- Est dynamioque
- Code dans /WebContent/
- Pas de code métier

------

##### <u>Integration Java</u>

Intégrer du code java dans du HTML :

```jsp
<!-- Sans affichage -->
<% /%>

<!-- Avec affichage -->
<%= %>
    
 <!-- include -->
 <%@ include file="filename.ext" %>
    
 <!-- import -->
 <%@page import="truc"%>
```



------

##### <u>Exemple</u>

Exemple de JSP

```jsp
<%@page import="java.util.Date"%>
<%@page import="java.text.SimpleDateFormat"%>
<%@ page language="java" contentType="text/html; charset=ISO-8859-1"
	pageEncoding="ISO-8859-1"%>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1">

<title>Ma premi�re JSP</title>

</head>
	<body>
		<%	Date d = new Date();
			SimpleDateFormat formater = new SimpleDateFormat( "dd/MM/yyyy H:mm:ss" );
			String s = formater.format(d);
		%>

		Bonjour, nous sommes le <font color="blue"> <%= s %> </font>.
	</body>
</html>
```

------

##### <u>Lien avec Servlet</u>

Exemple de lien avec un servlet:

```jsp
<%@page import="servlet.MonServlet"%>
<%@page import="java.text.SimpleDateFormat"%>
<%@ page language="java" contentType="text/html; charset=ISO-8859-1"
	pageEncoding="ISO-8859-1"%>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1">
<title>identification</title>
</head>

<body>
    <!-- Dans action on appelle un servlet -->
	<form name="identificationForm" method="post" action="MonServlet">
		<table name="Formulaire">
		<tr>
			<td><b>Nom : </b></td>		<td><input type = "text" name="nom"></td>
		<tr>
			<td><b>Mdp :</b></td>		<td><input type="password" name="mdp"></td>
		</tr>
		</table>
	<input type="reset" value="raz">
	<input type="submit" value=":)" >
	</form>
</body>

</html>
```

------

##### <u>Balise Usebean</u>

Prérequis : 

- Déclarer un bean dans le servlet contôleur (*setAttribute(String, Object)*)
- Utiliser les balises usebean dans le JSP

```Jsp
<!-- creation du bean en local -->
<jsp:usebean id="maPersonne" class="monBean"></jsp:usebean>

<!-- get et set du bean -->
<jsp:getProperty property="nomPropriété" name="nomBean" />
<jsp:setProperty property="nomPropriété" value="Alexandra" name="nomBean" />
```



------

##### <u>Déconnexion</u>

Pour se déconnecter il faut invalider la session

```Java
session.invalidate();
```



------

