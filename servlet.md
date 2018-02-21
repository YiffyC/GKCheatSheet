## Servlet 

------

- Conteneur web
- Les servlets sont éxécutés côté serveur.
- Non visible si pas compilé
- Code dans /src/
- Réponds à la requête du client

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

Redirection vers une url : 

```java
public void redirection(String url, HttpServletResponse response) throws IOException
	{
		response.sendRedirect(url);
	}
```



------

