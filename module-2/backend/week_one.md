## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

1. List the five common HTTP verbs and what the purpose is of each verb.
GET-Retrieves information
POST-Send information/manipulates data
PUT-Manipulates data and updates view
DELETE-Deletes data specified by request

2. What is Sinatra?
A domain-specific-language used for creating web applications. 

4. What is MVC?
Model-view-controller is an architecture for creating web applications. Models set the rules, views are how information is displayed, and the controller processes all of the information.

5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
Following RESTful convention aids in readibility and portability for developers. 

6. What types of variables are accessible in our view templates without explicitly passing them?
Instance variables.

7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
  
  ```ruby
  get '/horses' do
    erb :index
  end
  ```
@count = 1

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed`?

locals => {:name => "Mr. Ed"}

9. What's the purpose of ERB?

To input Ruby code into a HTML document. 

10. Why do I need a development AND test database?

To avoid manipulating the development database during testing. 

11. What's responsive design?

Designing web pages that are scalable. This is helpful for site viewability across platforms. 

12. What is CRUD and why is it important?

Create, read, update, delete. This refers to the manipulation of data within a database. 

13. What does HTTP stand for? 

Hyptertext transfer protocol

14. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?

<%= ruby code %>
<% ruby code %>

The first inserts the value of a Ruby expression, while the second executes the code without inserting the return value.

15. What's an ORM?

Object relational mapping software creates objects out of non-OO data within OOP languages.

16. What's the most commonly used ORM?

For Ruby, Active Record is what we're using. It is based on the creation and manipulation of tables within a database. 

17. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.

get '/restaurants' do
  @restaurants = Restaurant.all
  erb: index
end

The initial GET request returns the restaurant ERB index page
 
get '/restaurants/new' do
  erb :new
end

A GET request is needed to send a user to a page to create a new restaurant

post '/restaurants' do
  restaurant = Restaurant.new(params[:restaurant])
  restaurant.save
  redirect '/restaurant'
end

When the new restaurant form is submitted, a POST request is sent where a new restaurant is created in the database and the user is redirected to the restaurant index page.

get '/restaurant/:id' do
  @restaurant = Restaurant.find(params[:id])
  erb :show
end

When navigating to a specific restaurant, a GET request displays the restaurant info.

get '/restaurant/:id/edit' do
  @restaurant = Restaurant.find(params[:id])
  erb :edit
end

When clicking an edit button or link, this GET request brings the user to an edit page to change its attributes

put '/restaurant/:id' do |id|
  Restaurant.update(id.to_i, params[:restaurant])
  redirect "/restaurant/#{id}"
end

PUT requests manipulate the data & update ths page

delete '/restaurant/:id' do |id|
  Restaurant.destroy(id.to_i)
  redirect '/restaurant'
end

DELETE requests delete data submitted from a button/link

18. What's a migration? 

A migration manipulates a table. It changes the database scheme file. 

19. When you create a migration, does it automatically modify your database?

Nope. You have to run db:migrate

20. How does a model relate to a database?

A model stores the methods and attributes of a table-turned-object. 
