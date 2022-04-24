## Routes

- Tüm route listesini görmek için

`php artisan route:list`

**Ekrana view çağırmak için;**

```php
Route::get('/', function () {
    return view('welcome');
});
```

**Ekrana string çağırmak için;**

```php
Route::get('/', function () {
    return "Hello Laravel";
});
```

**URL değiştirerek ekrana view çağırmak için;**

```php
Route::get('/hi', function () {
    return view('welcome');
});
```

**Parametre göndermek için;**

```php
Route::get('/users/{id}', function ($id) {
    return "users id : ". $id;
});
```

**Varsayılan değeri olan parametre göndermek için;**

- Bu parametre gönderilmese bile hata vermez.

```php
Route::get('/users/{id?}', function ($id = null) {
    return "users id : ". $id;
});
```

**Birden fazla parametre göndermek için;**

```php
Route::get('/users/{id}/{name}', function ($id, $name){
    return "$id numaralı kullanıcı adı : $name";
});
```

**Route'a erişim için name atamak;**

- Bu yöntem ile route'a `route('users')` komutuyla erişebiliriz.

```php
Route::get('/users/edit/process', function () {
    return 'hi users';
})->name("users");
```

**Route'ı controller içerisindeki method'a bağlamak için;**

- use komutu ile controller dosyamızı web.php route dosyamıza dahil ediyoruz.
- home içerisindeki index methoduna bağlanıyoruz.

```php
use App\Http\Controllers\homeController;

Route::get('/home',
    [homeController::class, 'index']
);
```

**Contoller içerisindeki show methoduna bağlanıp get ile parametre gönderiyoruz**

```php
use App\Http\Controllers\homeController;

Route::get('/home/{id}',
    [homeController::class, 'show']
);
```

**Post methodu ile route belirlemek için;**

```php
use App\Http\Controllers\homeController;

Route::post('/home/store',
    [homeController::class, 'store']
);
```

**Put methodu ile route belirlemek için;**

```php
use App\Http\Controllers\homeController;

Route::put('/home/{id}',
    [homeController::class, 'edit']
);
```

**Controller içerisindeki tüm methodlara tek seferde route atamak için;**

```php
use App\Http\Controllers\homeController;

Route::resource('home', homeController::class);
```

**Controller route group oluşturmak için;**

```php
use App\Http\Controllers\CategoryController;

Route::controller(CategoryController::class)->group(function () {
    Route::get('panel/category', 'index')->name('panel.category');
    Route::get('panel/category/add', 'create')->name('panel.category.add');
});
```
