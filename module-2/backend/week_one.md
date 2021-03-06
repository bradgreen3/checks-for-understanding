## Week One - Module 2 Recap

1. List the five common HTTP verbs and what the purpose is of each verb.
  <br>
  GET-Retrieves information
  <br>
  POST-Send information/manipulates data
  <br>
  PUT-Manipulates data and updates view
  <br>
  DELETE-Deletes data specified by request

2. What is Sinatra?
<br>
A domain-specific-language used for creating web applications.

3. What is MVC?
<br>
Model-view-controller is an architecture for creating web applications. Models set the rules, views are how information is displayed, and the controller processes all of the information.

4. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
<br>
Following RESTful convention aids in readibility and portability for developers.

5. What types of variables are accessible in our view templates without explicitly passing them?
<br>
Instance variables.

6. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?

  ```ruby

    get '/horses' do
      erb :index
    end
  ```
  ```ruby
  @count = 1
  ```

7. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed`?

  ```ruby
  locals => {:name => "Mr. Ed"}
  ```

8. What's the purpose of ERB?
<br>
To input Ruby code into a HTML document.

9. Why do I need a development AND test database?
<br>
To avoid manipulating the development database during testing.

10. What's responsive design?
<br>
Designing web pages that are scalable. This is helpful for site viewability across platforms.

11. What is CRUD and why is it important?
<br>
Create, read, update, delete. This refers to the manipulation of data within a database.

12. What does HTTP stand for?
<br>
Hyptertext transfer protocol

13. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?

  ```erb
  <%= ruby code %>
  <% ruby code %>
  ```

  The first inserts the value of a Ruby expression, while the second executes the code without inserting the return value.

14. What's an ORM?

  Object relational mapping software creates objects out of non-OO data within OOP languages.

15. What's the most commonly used ORM?

  For Ruby, Active Record is what we're using. It is based on the creation and manipulation of tables within a database.

16. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.

  ```ruby
  get '/restaurants' do
    @restaurants = Restaurant.all
    erb: index
  end
  ```

  The initial GET request returns the restaurant ERB index page

  ```ruby
  get '/restaurants/new' do
    erb :new
  end
  ```

  A GET request is needed to send a user to a page to create a new restaurant

  ```ruby
  post '/restaurants' do
    restaurant = Restaurant.new(params[:restaurant])
    restaurant.save
    redirect '/restaurant'
  end
  ```

  When the new restaurant form is submitted, a POST request is sent where a new restaurant is created in the database and the user is redirected to the restaurant index page.

  ```ruby
  get '/restaurant/:id' do
    @restaurant = Restaurant.find(params[:id])
    erb :show
  end
  ```

  When navigating to a specific restaurant, a GET request displays the restaurant info.

  ```ruby
  get '/restaurant/:id/edit' do
    @restaurant = Restaurant.find(params[:id])
    erb :edit
  end
  ```

  When clicking an edit button or link, this GET request brings the user to an edit page to change its attributes

  ```ruby
  put '/restaurant/:id' do |id|
    Restaurant.update(id.to_i, params[:restaurant])
    redirect "/restaurant/#{id}"
  end
  ```

  PUT requests manipulate the data & update ths page

  ```ruby
  delete '/restaurant/:id' do |id|
    Restaurant.destroy(id.to_i)
    redirect '/restaurant'
  end
  ```

  DELETE requests delete data submitted from a button/link

17. What's a migration?

  A migration manipulates a table. It changes the database scheme file.

18. When you create a migration, does it automatically modify your database?

  Nope. You have to run db:migrate

19. How does a model relate to a database?

  A model stores the methods and attributes of a table-turned-object.
