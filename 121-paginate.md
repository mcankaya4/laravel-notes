## Paginate

```php
Route::get('/', function () {
    $products =  Product::paginate(3);

    foreach ($products as $product) {
        echo $product->name;
        echo "<br>";
    }

    echo $products->links();
});
```
