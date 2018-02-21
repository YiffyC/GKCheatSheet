## Servlet 



[TOC]



------

##### Résumé

- Conteneur web
- Les servlets sont éxécutés côté serveur.
- Non visible si pas compilé
- Code dans /src/
- Réponds à la requête du client

------

##### <u>Servlet classique :</u>

```java
@WebServlet("/MonServlet")
public class MonServlet extends HttpServlet {
	private static final long serialVersionUID = 1L;
       
    /**
     * @see HttpServlet#HttpServlet()
     */
    public MonServlet() {
        super();
        // TODO Auto-generated constructor stub
    }

	/**
	 * @see HttpServlet#doGet(HttpServletRequest request, HttpServletResponse response)
	 */
	protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		// TODO Auto-generated method stub
		response.getWriter().append("Served at: ").append(request.getContextPath());
		faire(request, response);
	}

	/**
	 * @see HttpServlet#doPost(HttpServletRequest request, HttpServletResponse response)
	 */
	protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		// TODO Auto-generated method stub
		doGet(request, response);
	}
}
```

*doGet()* et *doPost()* ne sont pas utilisées en même temps mais corresponent à l'utilisation ou non du cache.

------

##### <u>Récupération d'informations d'un formulaire</u>

Implémentation de la méthode *faire()* qui récupère les élémenyts du formulaire ainsi que les valeurs associées :

```java
private void faire(HttpServletRequest request, HttpServletResponse response)
	{
    	//récuperation de la liste des paramètres
		Enumeration<String> params =request.getParameterNames();
		
		while(params.hasMoreElements())
		{
			String key = params.nextElement();
            //affichage des valeurs
			System.out.println(key + ": " + request.getParameter(key));
		}

	}
```



------

##### <u>Redirection vers une url</u> 

```java
public void redirection(String url, HttpServletResponse response) throws IOException
	{
		response.sendRedirect(url);
	}
```



------

##### <u>Chaînage de Servlets</u>

Utilisation des chainages plutot que la redirection dans la pratique pour garder la logique métier. Pour se faire, il faut utiliser le *requestDispatcher* 



Servlet1 appelant Servlet2 par inclusion:

```Java
void service(HttpServletRequest request, HttpServletResponse response)
{
    /*
    * traitement
    */
    
    ServletContext sc = getServletConfig().getServletContext();
    RequestDispatcher rd = sc.getRequestDispatcher("/Servlet2");
    rd.include(request, response);
    //suite des traitements
}
```



Servlet1 appelant Servlet2 par délegation:

```java
void service(HttpServletRequest request, HttpServletResponse response)
{
    /*
    * traitement
    */
    
    ServletContext sc = getServletConfig().getServletContext();
    RequestDispatcher rd = sc.getRequestDispatcher("/Servlet2");
    rd.forward(request, response);
    //aucun traitement pour répondre à l'utisateur, le servlet2 l'a fait
}
```

