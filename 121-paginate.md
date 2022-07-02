## Paginate

php artisan vendor:publish --tag=laravel-pagination

```php
Route::get('/', function () {
    $products =  Product::paginate(3);

    foreach ($products as $product) {
        echo $product->name;
        echo "<br>";
    }

    echo $products->links('vendor.pagination.bootstrap-4');
});
```
