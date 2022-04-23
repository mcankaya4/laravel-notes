## Views

**Controller'dan view'e veri göndermek için;**

```php
public function setData()
{
    return view('welcome', ['getId'=> $id]);
}
```