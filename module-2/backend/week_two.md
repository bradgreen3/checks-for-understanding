## Week Two - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!).

Note: When you're done, submit a PR.

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
It is a DSL that allows you to treat tables within a SQL database as Ruby objects.
2. What kind of methods are `belongs_to`, and `has_many`? (i.e. class or instance) Give an example.
Class methods. A horse belongs_to a stable, and a stable has_many horses.
3. What do they allow you to do?
Create associations between two tables.
4. What's the difference between agile workflow and waterfall method?
Waterfall is sequential--planning, designing, creating, testing. You know the outcome you want beforehand. Agile is incremental. You tackle a project in iterations, for instance. You don't typically know what the outcome until you get there.
5. What is the difference between `#new` and `#create`?
These are methods. #new usually takes you to a form to create a new thing, whereas #create is the method called when pressing a submit button on said form.
6. At a basic level, what does cURL allow you to do?
Send/receive information to/from a server.
7. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.
I understand that a join table is needed for this many-to-many relationship, but I don't fully understand why. Nevertheless, students has_many students_teachers and has_many :teachers, through: :students_teachers. Students_teachers belongs_to :students and belongs_to :teachers. Teachers has_many students_teachers and has_many students, through: :students_teachers.
8. Define foreign key, primary key, and schema.
A foreign key is an ID linking an object within one table to an object within another. A primary key is assigned to each new object/row that is created within a table. In short, it references an object within a single, local table. A schema is a file that displays the tables and their attributes/columns within a database.
9. Describe the relationship between a foreign key on one table and a primary key on another table.
Each object within a table will(?) have a primary key. If those objects are linked to an object within another table, then they will be linked via the primary key of the foreign object. This is a foreign key. That was more difficult to explain than it should've been.
10. What are the parts of an HTTP response?
A status code (e.g. 200), lengthy header information that I don't really remember, and the body which contains a message describing the response from the server.
11. Describe some techniques to make our Sinatra code more DRY. Give an example of when you would use these techniques.
Create test data methods to avoid retyping data (e.g. payloads). Use a layout view to avoid retyping shared HTML.


### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
.where is cool. It finds everything matching the query. find_or_create_by is alright too. If it finds the query, it returns its ID, otherwise it creates it for you.
2. Name your three favorite ActiveRecord rake tasks and describe what they do.
rake db:create ||| creates the database
rake db:migrate ||| runs the migration/edits schema file
rake db:rollback ||| undos the last migration run
4. What can you expect from a group as you begin working together? As you continue working together?
DTR. Check in with how well we're following our DTR.
5. What two columns does `t.timestamps null: false` create in our database? created_at and updated_at
6. What cURL flag can you use to send a `POST` request?
-d
7. What case does JSON (and JavaScript) use for multi-word variables? camelCase
8. What case does Ruby use for multi-word variables?
snake_case
9. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
Most likely, one-to-many
10. In the same database, what will you need to do to create this relationship (draw a schema diagram)? Teacher belongs_to school, school has_many teachers. A foreign key column for schools is needed in the teachers table.
11. Give an example of when you might want to store information besides ids on a join table. Can't think of any off the top of my head :-(
12. Describe and diagram the relationship between patients and doctors. Patient belongs_to doctor, doctor has_many patients.
13. Describe and diagram the relationship between museums and original_paintings. One to one?
14. What are some examples of acceptable values for the parts of an HTTP response? I don't understand this question.
15. What types of output do we want to test when we test our controllers? You're testing the application's response to an incoming request, so you're testing to see if the application redirects you to where you expect to go based on the incoming request.
16. What could you see in your code that would make you think you might want to create a partial? Repeated material.
17. Why might you use a helper method? DRY.
