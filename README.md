# Backend REST API

## technologies

- PHP7  

- PDO

- MySql

- Javascript

## Dependencies

- MySql 

- PDO

## Steps
 
# Download and transfer project files

### 1) Clone the repository, first must create an user sql for our application

``` 
git clone https://github.com/agloks/php-dck.git
mysql -U <youruser> -p < sql_user.sql
```

### 2) Then create our database and fill it with account was created at script above. (password is 123).

```
mysql -U challenge - p < sql_create.sql
```

### 3) Up server on port 8000 and at folder that contain the index.php.

```
php -S 127.0.0.1:8000
```

## Create Methods

### Product

Create `Produto` calling route POST: http://localhost:8000/api/V1/product/create/ :

 Key| Description| Required
 ---|---|---
 `name`       | product name.             | **Yes**
 `sku`      | product code sku.                            | **Yes** , <br> Unique: `true`.
 `price`  | price product.                         | No, <br> Default setting: `0`.
 `quantity` | number of product.					| No, <br> Default setting: `0`.
 `categories`  | code of category on db                        | No
 `description`  | description product                         | No, <br> Default setting: `Empty`.

### Category

Create `Categorias` using calling route POST: http://localhost:8000/api/V1/categories/create/ :

 Key| Description| Required
 ---|---|---
 `name`       | name of category.             | **Yes**
 `code`      | code of category.                            | **Yes** <br> Unique: `true`.


## Remove Methods

### Product

Remove any value in `Produto` calling route PATCH: http://localhost:8000/api/V1/product/remove/ :

 Key| Description| Required
 ---|---|---
 `name`       | write as value = "remove"             | No
 `sku`      | code of sku don't is able to remove                            | **Yes**
 `price`  | write as value = "remove"                         | No
 `quantity` | write as value = "remove"							| No
 `categories`  | write as value = "remove"                       | No
 `description`  | write as value = "remove"                         | No

### Category

Remove any value in `Categorias` using calling route PATCH: http://localhost:8000/api/V1/categories/remove/ :

 Key| Description| Required
 ---|---|---
 `name`       | write as value = "remove"             | No
 `code`      | code of category don't is able to remove                           | **Yes**


## Update Methods

### Product

Update any value in `Produto` calling route PUT: http://localhost:8000/api/V1/product/update/ :

 Key| Description| Required
 ---|---|---
 `name`       | product name.             | No
 `sku`      | code of sku don't is able to remove                            | **Yes**
 `price`  | price product.                         | No
 `quantity` | number of product.					| No
 `categories`  | here is to add more categories to product                        | No
 `description`  | description product                         | No

### Category

Remove any value in `Categorias` calling route PUT: http://localhost:8000/api/V1/categories/update/ :

 Key| Description| Required
 ---|---|---
 `name`       | category name.             | No
 `code`      | code of category don't is able to remove                           | **Yes**


## Delete Methods

### Product

Delete `Produto` calling route DELETE: http://localhost:8000/api/V1/product/delete/ :

 Key| Description| Required
 ---|---|---
 `sku`      | product code sku.                            | **Yes**

### Category

Delete `Categorias` calling route DELETE: http://localhost:8000/api/V1/categories/delete/ :

 Key| Description| Required
 ---|---|---
 `code`      | code of category.                           | **Yes**


## Tests

They were fully realized with shell script because don't need download anything, automating the call in api, and proving success of each route. 
To execute test, go to folder tests, so give permission for script and execute it.
``` 
chmod +x test-routes.sh
./test-routes.sh <payload>
`
