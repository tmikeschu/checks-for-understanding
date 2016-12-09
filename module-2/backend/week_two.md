## Week Two - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!). 

Note: When you're done, submit a PR. 

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
  * ActiveRecord is an example of Object Relational Mapping. It is an API that facilitates the communication between Ruby/Rails and a SQL database. Most simply, we can make queries to the database in Ruby-y language.
  
2. What kind of methods are `belongs_to`, and `has_many`? (i.e. class or instance) Give an example.
  * These are instance methods. An instance of a model can call one of these association methods to find its related data. E.G., a school has many students, but a has many method `:students` would apply to a specific school, not the abstract idea of School (~class). The same applies for a student, who belongs to a school at a given time.
  
3. What do they allow you to do?
  * These methods can get information related to an object while keeping a normalized database schema.

4. What's the difference between agile workflow and waterfall method?
  * They exist on a spectrum. On the more agile side, workflow is iterative and made up of a series of completion points where a product/project is fully functional in a given context. Waterfall approaches consist of one big completion point, where things either work entirely, or not at all. Agile allows for frequent adjustments and pivots to realistic demands and requirements.
  
5. What is the difference between `#new` and `#create`?
  * #new instantiates an object of an ActiveRecord model, whereas #create both instantiates an object and saves it to the database.
  
6. At a basic level, what does cURL allow you to do?
  * Curl allows the user to see the http request/response cycle happening under the hood of a client-server interaction.
  
7. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.
  * Woah! I promise I didn't look at this for answer 2. The students would be related to teachers through something like a Classes join table. Classes would have the foreign keys of student_id and teacher_id. Students would have many classes and many teachers through classes. Teachers would have many classes and many students through classes.
  
8. Define foreign key, primary key, and schema.
  * A foreign key is an integer value in a table that references the primary key of an object in another, related table. A primary key is a unique identifier of a table row (and/or Ruby object).

9. Describe the relationship between a foreign key on one table and a primary key on another table.
  * An FK on one table is the same is the PK on the second table to which the first table refers.
  
10. What are the parts of an HTTP response?
  * Header (protocol), body and content length, response code.
  
11. Describe some techniques to make our Sinatra code more DRY. Give an example of when you would use these techniques.
  * Create a helper module for the controller that takes care of methods, such as formatting data. In testing, setting a before block of seed data to use in all the tests. In the models, creating methods that can take in a method symbol so similar queries can be used for multiple table columns/attributes. 


### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
  * .maximum finds the max of an attribute, .minimum does the same. .joins is awesome for grouping and ordering by a relational attribute. .where is like #find_all in Ruby, and you can pass it a range as an argument! The .joins(:table).group(:attribute).count makes a sweet hash of the :attribute keys pointing to their count.
  
2. Name your three favorite ActiveRecord rake tasks and describe what they do. 
  * I mean how can you not love rake db:create_migration NAME=command_description? I'd be lost without it. I also love rake db:test:prepare, because it creates a nifty test database that I can use without affecting the production data. Lastly, what would I do without rake db:migrate? I make all these migrations and specify data types and timestamps, and it's all for nothing unless I rake db:migrate to my database!
  
4. What can you expect from a group as you begin working together? As you continue working together?
 * I always expect some awkward figurings out of how each other works. I get through this by explicitly and humorously acknowledging tension and awkwardity (I wish that was a word). I also expect to learn what peoples' learning goals are for the project, and what they are nervous about and excited for. As work progresses, I keep adaptability in mind, because behaviors can emerge from people that they are not aware of and may not have mentioned. Productivity can also increase as group members grow to know each other's style and quirks. It also gets more fun (ideally)!
 
5. What two columns does `t.timestamps null: false` create in our database?
 * created_at and updated_at
 
6. What cURL flag can you use to send a `POST` request?
 * No clue.
 
7. What case does JSON (and JavaScript) use for multi-word variables?
 * thisOne amIRight?
 
8. What case does Ruby use for multi-word variables?
 * snake_case
 
9. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
 * Typically, one-to-many (school-to-teachers).

10. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
 * I need the foreign key of schools.id in the teachers table, and association methods in the models.
```
def create_table :teachers do |t|
 t.string :name
 t.integer :school_id
 
 t.timestamps null: false
end

def create_table :schools do |t|
 t.string :name
end
```

11. Give an example of when you might want to store information besides ids on a join table.
 * Other unique identifiers, like date or a composition of author and title for a book.
 
12. Describe and diagram the relationship between patients and doctors.
 * A patient could have many doctors or just one doctor. Basically all doctors have many patients. They would be related through a Doctors-Patients join table, where each row holds a foreign key of doctor_id and patient_id. Both parties have many of their counterparts through that join table.
 
13. Describe and diagram the relationship between museums and original_paintings.
 * An original_painting belongs to one museum, and a museum has many original_paintings.

14. What are some examples of acceptable values for the parts of an HTTP response?
 * Protocol: http.

15. What types of output do we want to test when we test our controllers?
 * Page content?

16. What could you see in your code that would make you think you might want to create a partial?
 * Nope.
 
17. Why might you use a helper method?
 * Refactor your controller. Distribute that responsibility!
