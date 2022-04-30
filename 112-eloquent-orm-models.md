## Models

**Accessors**

- DB'den gelen verileri belli bir standartta göstermek için kullanılır.
- Örn: Gelen name değerlerini büyük getirsin.

```php
public function getNameAttribute($value)
{
    return mb_strtoupper($value, 'UTF-8');
}
```

```php
User::find(1)->name;
```

**Mutators**

- DB'ye giden verileri belli bir standartta göndermek için kullanılır.
- Örn: Gelen name değerlerinin hepsini büyük harfle kayıt etsin.

```php
public function setNameAttribute($value)
{
    $this->attributes['name'] = mb_strtoupper($value, 'UTF-8');
}
```

```php
User::create(['name'=>'eylül']);
```

**Append Custom**

- DB'den çekilen verileri birleştirerek veya ayırarak yeni bir sütun gibi çekmek için kullanılır.
- Örn: name ve surname değerleri ayrı biz bunlar username adında yeni bir sütun gibi çekebiliriz.

```php
public function getNameSurnameAttribute(){
    return $this->name. " " . $this->surname;
}

protected $appends = ['name_surname'];
```

```php
User::find(1);
User::find(1)->name_surname;
```