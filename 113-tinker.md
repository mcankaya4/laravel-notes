## Tinker

- CRUD işlemlerini terminalden yapmamızı sağlar.

`php artisan tinker` ile başlatıyoruz.

**CREATE**

```php
Tag::create(['title'=>'laravel', 'desc'=>'açıklama metni']);
```

**READ**

```php
Tag::all();
```

**UPDATE**

```php
Tag::find(1)->update(['title'=>'PHP'])
```

**DELETE**

```php
Tag::find(1)->delete();
```

