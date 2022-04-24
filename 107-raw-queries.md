## Raw Queries

- DB sınıfı dahil edilerek yapılan sorgulardır.
- Klasik SQL şeklinde yazılır.

**CREATE**

```php
use Illuminate\Support\Facades\DB;

DB::insert(
    'insert into categories (title, slug, parent_id) values (?,?,?)',
    ['Vazo Dilleri', 'vazo-dilleri', 0]
);
```

**READ**

```php
use Illuminate\Support\Facades\DB;

DB::select('select * from categories');
```

```php
use Illuminate\Support\Facades\DB;

DB::select('select * from categories where id=?', [2]);
```

**UPDATE**

```php
use Illuminate\Support\Facades\DB;

DB::update(
    'update categories set title=? where id=?',
    ['Macbook',2]
);
```

**DELETE**

```php
use Illuminate\Support\Facades\DB;

DB::delete('delete from categories where id=?', [2]);
```