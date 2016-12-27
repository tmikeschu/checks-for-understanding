## Week Four Recap

### Instructions
Fork this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

* What is a cookie?

  * A cookie is a hash-like object of information about a user that relates to the application
  
* What’s the difference between a session and a cookie?

  * A session is a special type of cookie, indicating a certain scope of the data and features available to a user.
  
* What’s a flash and when do you want to use flashes?
  
  * A flash is a special cookie used to communicate with the user, usually about errors or successes.
  
* Why do people say “HTTP is stateless”?

  * The HTTP cycle by itself cannot remember any information beyond its cycle.
  
* What’s authentication? Explain.

  * Authentication is verifying who a user is based on existing credentials in the database
  
* What’s the difference between authentication and authorization?

  * Authorization requires authentication first, and then specifies what a given user is able to do in the application.
  
* What’s a before filter?

  * It runs defined methods before a controller action is executed.

* How do we keep track of a user once they’ve logged in?

  * With sessions (e.g., session[:user_id]).
 
* When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?
  
  * Namespacing is ideal for clarity and distributed responsibility (e.g., we can expect one resource namespaced within :admin to have different responsibilities from that same resource defined outside of the :admin namespace.
  * Nesting resources often reflects a one to many relationship, with the "one" wrapping the "many".
  * As I understand it, a namespace attribute is not necessarily a model in the database, while nested resources probably are and have defined associations with each other.
  
* At a high level, what tools can you use to implement authorization? How would you use them?

  * Setting a role attribute for user, and using the :enum method to define these roles. For example, a user could have a role of 0 or 1, and the enum in the model could define these as "default" and "admin". Once these are defined, we can control which controller actions and which views are available to a given user role.

* What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?

  * Must have missed the previous question? It offers the advantage of not having to type "default" and "admin", for example, over and over and over. It also provides some built in boolean methods, such as `.admin?`. The database datatype for an enum needs to be an integer, an integer which refers to an index slot in the enum array. Declare it in the model.
  
* What are some strategies you can use to keep your views DRY?

  * I like using helper methods for formatting, and special getter methods for the model. Partials are also essential! If I find myself using a shared partial frequently, I'll also move it to the application layout view.
  
