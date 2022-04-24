## Query Builders

- DB sınıfı dahil edilerek yapılan sorgulanabilir.
- Model üzerinden sorgulanabilir.

**CREATE**

```php
use Illuminate\Support\Facades\DB;

DB::table('categories')
    ->insert([
        'title' => 'Mouse',
        'slug' => 'mouse',
        'parent_id' => 1
    ]);
```

or

```php
use App\Models\Category;

Category::insert([
        'title' => 'Mouse',
        'slug' => 'mouse',
        'parent_id' => 1
    ]);
```

**READ**

```php
use Illuminate\Support\Facades\DB;

DB::table('categories')
    ->get();

DB::table('categories')
    ->first();

DB::table('categories')
    ->where('id','=',3)
    ->get();

DB::table('categories')
    ->orderByDesc('id')
    ->get();
```

or

```php
use App\Models\Category;

Category::get();

Category::first();

Category::where('id','=',3)
    ->get();

Category::orderByDesc('id')
    ->get();
```

**UPDATE**

```php
use Illuminate\Support\Facades\DB;

DB::table('categories')
    ->where('id','=',3)
    ->update([
    'title' => 'değişim zamanı'
]);
```

or

```php
use App\Models\Category;

Category::where('id','=',3)
    ->update(
        'title' => 'değişim zamanı'
    );
```

**DELETE**

```php
use Illuminate\Support\Facades\DB;

DB::table('categories')
    ->where('id','=',3)
    ->delete();
```

or

```php
use App\Models\Category;

Category::where('id','=',3)
    ->delete();
```
