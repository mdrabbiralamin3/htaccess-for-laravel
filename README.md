# htaccess-for-laravel
We all know that, we can not directly run laravel project from localhost. We have to run php artisan serve command for that. But using this .htaccess file in root folder we can directly run our project from localhost.

# htaccess-for-subfolder
We also know that, we can not directly run laravel project from localhost/subfolder also. We have to run php artisan serve command for that. But using this .htaccess-for-subfolder file in root folder we can directly run our project from localhost.

**folder for running laravel project inside subfolder structure will be**
/root
    /<subfolder>/
        /public/
            index.php
            login
            .htaccess // laravel default htaccess
        .htaccess // your generated htaccess

**Note that you need to add below content in your env**
APP_URL=http://example.com/<subfolder>
ASSET_URL=http://example.com/<subfolder>
APP_DIR=<subfolder>

**Keep all your routes inside APP_DIR subfolder**
$prefix = env('APP_DIR', ''); // Defaults to empty if APP_DIR is not set
Route::prefix($prefix)->group(function () {
    // All your routes
});
