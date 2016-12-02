## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

1. List the five common HTTP verbs and what the purpose is of each verb.
 * GET views a page
 * POST adds data
 * PUT/PATCH updates data
 * DELETE destroys data

2. What is Sinatra?
 * A server framework in which we can run Ruby code.

4. What is MVC?
 * Model(data)-View(output)-Controller(routes) set up for an application.  

5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
 * This helps us share a common language/understanding with other developers, which allows us to collaborate and debug with more efficiency.
 
6. What types of variables are accessible in our view templates without explicitly passing them?
 * Instance variables
 
7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
  
  ```ruby
  get '/horses' do
    erb :index
  end
  ```
 * Just set `@count = 1` above the erb method, and `@count` is available in the `:index` file.
 
8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed`?
 * Append `, locals: name: "Mr. Ed"` to the erb line. 
 
9. What's the purpose of ERB?
 * It allows us to run Ruby code within HTML code. 
 
10. Why do I need a development AND test database?
 * We want to test that the database is CRUD-able, but we don't want to actually manipulate the 'production' database just for test data.
 
11. What's responsive design?
 * Building apps to account for variable view environments of a user's device.
 
12. What is CRUD and why is it important?
 * CRUD refers to apps/dbs that can Create, Read, Update, and Delete data. It is important because it allows the user to interact with a dynamic interface.
 
13. What does HTTP stand for? 
 * hypertext transfer protocol
 
14. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
 * <% %> evaluates a ruby expression (e.g., an enumerable on a collection) with no visible output
 * <%= %> displays the output of a ruby expression
 
15. What's an ORM?
 * object relational model. A database that creates normalized tables with relationships to each other.
 
16. What's the most commonly used ORM?
 * SQL
 
17. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
 * GET '/restaurants' displays (Reads) all the restaurant instances.
 * GET '/restaurants/new' displays a form to Create a new restaurant instance.
 * POST '/restaurants' adds (Creates) a restaurant instance from the '/new' form to the restaurants table.
 * GET '/restaurants/:id' displays (Reads) the data from a single restaurant, identified by its ID number.
 * GET '/restaurants/:id/edit' displays a form to edit (Update) a restaurant instance.
 * PUT '/restaurants/:id' edits (Updates) the restaurant instance with the data from the previous form.
 * DELETE '/restaurants/:id' removes (Deletes) a restaurant (using its id) from the database.
 
18. What's a migration? 
  * A migration sets up the architecture for a new table in the database.

19. When you create a migration, does it automatically modify your database?
  * NO! You have to run rake db:migrate
  
20. How does a model relate to a database?
 * A model has the responsibility of interacting with and extracting data from the database.
 
21. What's the difference between agile workflow and waterfall method?
 * Agile consists of constant and iterative accomplishments of functional features (e.g., one route at a time). Waterfall consists of one "big" accomplishment, hoping that the entire thing works.
 
22. What is the difference between `#new` and `#create`?
 * #new creates an instance of a Ruby class object, whereas #create both creates an instance and saves it in the database.
