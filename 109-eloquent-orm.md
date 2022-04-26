## Eloquent ORM

**MASS ASSIGMENTS**

- `$fillable = []` izin verilenler.
- `$guarded = []` izin verilmeyenler.
- `$table = ""` db table adı.

```php
class Category extends Model
{
    use HasFactory;
    
    protected $fillable = ['title','slug','parent_id'];
}
```

**CREATE**

```php
Category::create([
    'title' => 'Tablet',
    'slug' => 'tablet',
    'parent_id' => 0
]);
```

**READ**

```php
use App\Models\Category;

Category::find(5);
```

```php
use App\Models\Category;

Category::all();
```

**UPDATE**

```php
use App\Models\Category;
Category::find(5)
    ->update(['title' => 'Picture']);
```

**DELETE**

```php
use App\Models\Category;

Category::find(5)
    ->delete();
```



