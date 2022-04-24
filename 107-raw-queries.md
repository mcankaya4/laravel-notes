## Raw Queries

- DB sınıfı dahil edilerek yapılan sorgulardır.
- Klasik SQL şeklinde yazılır.

**CREATE**

```php
DB::insert(
    'insert into categories (title, slug, parent_id) values (?,?,?)',
    ['Vazo Dilleri', 'vazo-dilleri', 0]
);
```

**READ**

```php
DB::select('select * from categories');
```

```php
DB::select('select * from categories where id=?', [2]);
```

**UPDATE**

```php
DB::update(
    'update categories set title=? where id=?',
    ['Macbook',2]
);
```

**DELETE**

```php
DB::delete('delete from categories where id=?', [2]);
```