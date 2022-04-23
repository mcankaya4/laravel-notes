##Controllers

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
