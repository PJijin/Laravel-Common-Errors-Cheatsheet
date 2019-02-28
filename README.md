# Laravel-Common-Errors-Cheatsheet

⚡ Laravel Common Error Cheatsheet for beginners. 

🔍 Use Ctrl + F to search for error 

---

 **Error 1**

    `SQLSTATE[HY000] [1045] Access denied for user 'root'@'localhost' (using password: YES) (SQL: select count(*) as aggregate from` users`where`email `= xxx@xx.com)`

**Solution**

Make sure the database details are correct on the .env file

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=your_database_name
DB_USERNAME=your_database_username
DB_PASSWORD=your_database_password

---

**Error 2**

`419 sorry your session has expired. please refresh and try again`

**Solution**

The error basically occurs when there is no csrf token field on the form post. Make sure you have  {{ csrf_filed() }} on the blade form.

---

**Error 3**
 
`404
Sorry, the page you are looking for could not be found.`

**Solution**

You have not added the Route. Go to routes/web.php and specify the route.

---

**Error 4**
 
`405 Method not allowed`

**Solution**

You have not added the Route or it is not in Route::post method . Go to routes/web.php and specify the route or modify the route to post method.

---

**Error 5**

`Class App\Http\Controllers\HomeController does not exist`

**Solution**

You have not created the HomeController file. Go to your terminal and run
 `php artisan make:controller HomeController`
 
 ---
 
 **Error 6** 

`Method App\Http\Controllers\HomeController::test does not exist.`

**Solution**

You have not created the specified method on HomeController. Here the test method is not added in HomeController. 

---

**Error 7** 

`View [sample] not found.`

**Solution**

The template blade file is not present on the specified directory. Make sure you have created the sample.blade.php file on resources/views folder.

---

**Error 8** 

`Class 'App\Http\Controllers\admin\Auth' not found `

**Solution**

To use the Auth Namespace you need to import it at the top. 
`Use Auth;`

---

**Error 9** 

`SQLSTATE[HY000] General error: 1364 Field 'email' doesn't have a default value`

**Solution**

You need to pass the value to the Model at the time of creating new record. Or you need to make the field nullable in migration ->nullable and run 
`php artisan migrate:fresh`

---
