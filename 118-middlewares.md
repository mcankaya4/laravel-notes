## Middlewares

- Route isteği ile Controller arasındaki ara katmandır diyebiliriz.
- `php artisan make:middleware MiddleWareName` olarak oluşturulur.

```php
public function handle(Request $request, Closure $next)
{
    // Yapılan istekler burada yapılır ve istekler doğruysa;
    return $next($request);
    // ifadesi kullanılır.
}
```

- kernel.php içerisinde oluşturulan middleware'ye alias atanmak zorundadır.

```php
protected $routeMiddleware = [
    'name' => \App\Http\Middleware\MiddleWareName::class,
];
```

- Route içerisinde kullanmak için;

```php
Route::middleware('auth')->group(function () {
    Route::get('/', [ManagerSystemController::class, 'index']);
});
```

- Birden fazla middleware kontrolü için;

```php
Route::middleware(['auth','name'])->group(function () {
    Route::get('/', [ManagerSystemController::class, 'index']);
});
```

- Controller içerisinde kullanmak;

```php
public function __construct()
{
    $this->middleware('status');
}
```

