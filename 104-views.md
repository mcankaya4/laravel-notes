## Views

**View içerisinden public dizinine ulaşmak için method;**

- public/img/img.png dosyasına ulaşır.

```php
{{asset('img/img.png')}}
```

**View'de htmlspecialchars kullanarak veriyi yazdırmak için;**

```php
{{$getId}}
```

**Form içerisinde TOKEN ve PUT belirlemek;**

```php
@method('PUT')
@csrf
```

**Form action ve get ile parametre göndermek için;**

```php
{{route('name', $id)}}
```

**Route ile active link vermek için;**

```php
{{ Route::currentRouteNamed('panel.settings.social') ? 'active' : '' }}
```

**Birden fazla Url ile active link vermek için;**

```php
{{ Request::is(['panel/category/*','panel/category']) ? 'active' : '' }}
```


