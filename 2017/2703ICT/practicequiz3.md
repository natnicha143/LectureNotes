

1. To achieve pagination in Laravel, which of the following statements are true:
* It uses paginate() and links() function
* paginate() is called from the controller file

2. Given products() is a function in the Manufacture class that defines the 1 to many relationship between manufactures and products. Which of the following code returns a Product object?
* Manufacturer::find(1)->products()->get()[0];
* Manufacturer::find(1)->products()->first();

3. 
```php
$this->validate($request, [
                'name' => 'required|max:255',
                'price' => 'required|numeric',
                'manufacturer' =>'exists:manufacturers,id'
                ]);
```
* The manufacturer with that id must exist in the manufacturers table

4. Which of the following statements about using URL parameters for state maintenance are true?
* All links on a page must be dynamically generated to include state information in the URL parameter.

5. In Laravel, database seeders are used for:
* Inserting default data in the database.

6. Which of the following code correctly inserts a new record into a table using Eloquent?
* Product::create(array('name' => 'Cheerios', 'price' => 2.00));
*   $product = new Product;
    $product->name = 'Ginger Beer';
    $product->price = 3.00;
    $product->save();

7. To make use of Object Relation Mapping in Laravel:
* A model class needs to be created
* The model class needs to extend Model

8. For a form to be able to upload images to the server, which additional attribute must the form have?
* enctype="multipart/form-data"

9. The validate() function, used for input validation is defined in?
* The Controller class.

10. Given the relationship between customers and orders is one-to-many. To represent this relationship in Laravel's model using Eloquent, the foreign key must be:
* in the order table, called customer_id. 

11. How does Laravel pass validation error message from controller to view?
* Errors are stored in $errors which is made available to all views in the web middleware group.

12. Which of the following is an example of using Hidden Form Field for state maintenance?
*  The use of {{csrf_field()}} to generate a hidden form field for cross site request forgery check.

13. Which line of code is equivalent to :

    $jobs = Job::query()->offset(30)->limit(30)->get();

* $job = Job::query()->take(30)->skip(30)->get();

14. Which SQL clause can be used to limit the number of results  returned (to help with implement pagination)?
* LIMIT

15. Select correct statements regarding the code below:

    $name = $input['name'];
    $products = Product::whereHas('manufacturer', function($query) use ($name){
        return $query->whereRaw('name like ?', array("%$name%"));
    })->get();

* The whereHas() function queries a table that is related to the Products table.
* The whereRaw() call compares the $name with manufacturer name.

16. What does the given function do:

    datetime(time, 'unixepoch')

* Converts a unix timestamp to SQL 

17. In a production environment, if we want to change the structure of the database, why shouldn't we just drop the existing tables then create new tables?
* Because we'll lose all existing data in those tables
* Because we can use alter table command to change the table's structure

18. Select the correct statements regarding the use of middleware in the profile route below:

    Route::get('profile', function () { 
        // the logic for the profile route goes here.
    })->middleware('auth');

* The profile route can only be executed when the user is authenticated.
* When the profile route is executed, and the user is not authenticated, then the user is redirected to the login page.

19. How does Object Relation Mapping provide object-oriented interface to relational database?
* Instance functions are provided to perform operations on an individual record.
* Class functions are provided to perform queries on the table.

20. Which of the following functions in a resource controller take an $id as a parameter?
* show()
* edit()
* update()

21. Select all correct statements about Laravel's resource controller:
* Resource controllers use standard REST approaches to define the URLs and HTTP methods to interact with the resource.
* Resource controllers assume that a particular base URL is a resource, and makes assumptions about how you view, list, create, update and delete records from that resource.

22. Which of the following correctly creates a DateTime object?
* new DateTime('@15336774');
* new DateTime("now");
* new DateTime("2016-5-20");
* new DateTime('tomorrow');

23. When the Laravel migrate command "php artisan migrate" is executed:
* All oustanding migranes are run.

24. Unix timestamps:
* Represent date/time as the number of seconds from 1 Jan 1970.

25. The Laravel artisan command used to view all the routes created in an application is:
* php artisan route:list

26. The belongsToMany() function is used for:
* Specify many-to-many relationship between two tables.

27. Which Laravel function sends SQL directly to query the database?
* DB::select()

28. What would be the equivalent Eloquent expression to the following SQL query:

    select * from products;

* Product:all();

29. To specify a 1:M relationship between manufacturer and product in Eloquent:
* in the Manufacturer class, define a function that contains: return $this->hasMany('Product');

30. Which of the following should be displayed when the user is currently logged in?
* The log out button.
* The user name.

31. Select INCORRECT statements about Laravel's pagination links() function.
* The look and feel of the pagination navigation links generated by links() cannot be changed.

32. Which of the following functions calls return a collection of results?
* Model::all()

33. Select the correct statements regarding Laravel's Auth::guest() function.
* Auth::guest() returns true if the user is not logged in.

34. Select correct statements regarding cookies:
* The content of the cookie is set by the server.
* Cookie data is associated with a URL and will be sent back to the server when the browser accesses the URL again.
* Cookies are stored by the browser(on the client side).
* Cookies contain name-values pairs.

35. Select incorrect statements regarding file upload.
* After a file is uplodaed from a form, Laravel automatically moves it ot the storage directory.

36. Which of the following mechanisms can be used to maintain state between pages?
* Cookies
* Session variables
* URL Parameters
* Hidden components

37. Given a Laravel table object stored in a variable $table, what does the following line of code do:

        $table->timestamps();

* It creates created_at and updated\_at columns in the table

38. When images are stored in the file systems:
* Database stores the filename and paths to the images.

39. Which of the following about Laravel's Schema class is correct?
* The scheme class can be used to create database tables.
* The schema class provides SQL equivalent commands/functionalities
* The same schema class code works with different database with subtly different SQL syntax.
* The schema class can be used to drop database tables.

40. Given two records, $manufacturer and $product, which of the following correctly sets the $manufacturer as the manufacturer of $product?
* $manufacturer->products()->save($product);
*   $product->manufacturer()->associate($manufacturer);
    $product->save();

41. Which of the following line of code in routes.php connects a POST request to the URL 'example.com/about' to the function about() in ExampleController?
* Route::post('about', 'ExampleController@about');

42. What data type is used to store encrypted passowrd?
* string

43. Select correct statements regarding Laravel's validation.
* We only need to specify validation rules, Laravel will perform the validation and generate error messages for us.

44. Given a Laravel table object stored in a variable $table, what does the following line of code do:
* Creates a column in the table called id which will be autoincrementing primary key (PK)

45. What is Laravel's naming convention for models?
* The model name must start with an upper class letter and be the singular of the plural table name.

46. In the given line of code, the value of $x is:

    $x = ceil(4.6);

* 5


