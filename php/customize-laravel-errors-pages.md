# Customize Laravel errors pages

We have two ways to customize error pages in Laravel. Here we will see the simplest, that is, creating each error page manually.

---

### Create file in views

For example, if we want to customize the 404 error (page not found) page, just create a file called 404.blade.php in the errors folder. The errors folder is not created by default by Laravel, it will have to be created by us.
The file path must be: **resources/views/errors/**

Once this is done, simply customize the error page. This is an idea of ​​how it could be customized.

```html
<!doctype html>
<html lang="{{ str_replace('_', '-', app()->getLocale()) }}">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>404 Page Not Found</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
  </head>
  <body>
    <div class="container mt-5 pt-5">
      <div class="alert alert-danger text-center" role="alert">
        <h2 class="display-3">404</h2>
        <p class="display-5">Oops! Page Not Found.</p>
      </div>
    </div>
  </body>
</html>
```