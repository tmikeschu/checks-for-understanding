## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What is the entry at the command line to create a new rails app?
  * rails new project_name
  
2. What do Models generally inherit from in rails?
  * Either ActiveRecord::Base or ApplicationRecord
  
3. What do Controllers generally inherit from in a rails project?
  * ApplicationController
  
4. How would I create a route if I wanted to see a specific horse in my routes fitle assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?
  * `resources :horses, only: [:show]`
  
5. What rake task is useful when looking at routes, and what information does it give you?
  * `rake routes` returns a list of HTTP verb and controller acion pairs, the routes URL path, and a path/url helper method name.

6. What is an example of a route helper? When would you use them?
  * E.g., `new_horses_path`. Anytime you find yourself typing in a url string, it's probably (definitely?) time to use a path helper. It's a method under the Rails hood that determines the url based on convention.

7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?
  * `_url` is more like an absolute path (full url), whereas `_path` is more of a path relative to the root path.

8. What are strong params and why are the necessary?
  * Strong params are a requirement fo saving objects in a Rails database. They ensure that no extra/malicious information can be submitted into the database, only the attribute title included in the `#permit()` method will be processed for instantiation.

9. What role does `form_for` play in helping us create our forms?
  * This Rails helper 'Ruby-fies' an HTML form in a way that is more readable and clear w/r/t what is being made and where it should be saved. The form collects the data that will eventually be used to save as a new object's attributes.
  
10. How does `form_for` know where to submit the user's input?
  * It reads the type of instance variable passed to its argument(s). If am object shell comes in (e.g., Horse.new), it knows to POST to `/horses`. If the object is already a Horse object, it knows to PUT to `horses/:id`.

11. Create a form using a `form_for` helper to create a new `Horse`. 
  * ```
  <%= form_for @horse do |f| %>
    <%= f.label :name %>
    <%= f.text_field :name %>
    
    <%= f.label :breed %>
    <%= f.text_field :breed %>
    
    <%= f.submit %>
  <% end %>
  ```
  
12. Why do we want to validate our models?
  * This adds a level of cleanliness to our database, further ensuring that each object has its necessary information and datatypes, where appropriate.
