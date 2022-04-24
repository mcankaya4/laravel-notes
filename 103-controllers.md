## Controllers

- İçerisinde crud işlemleri için methodlar tanımlanmış controller oluşturmak için;

`php artisan make:controller UserController --resource`

**Controllers'dan view'e veri göndermek için;**

```php
public function index()
{
    $id = 10;
    return view('welcome', ['id' => $id]);
}
```

**Controllers yönlendirmeleri için;**

```php
public function go(){
    return redirect()->route('name');
    return redirect()->back();
}
```

**Controllers içerisinde public dizinine erişmek için;**

- public/asset/img.png içerisine erişir.

```php
public_path('asset/img.png')
```
