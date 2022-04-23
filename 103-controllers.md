## Controllers

**Resource yapısı ile gelen controller örneği**

```php
namespace App\Http\Controllers;

use Illuminate\Http\Request;

class CategoryController extends Controller
{
    public function index()
    {
	$id = 10;
	return view('welcome', ['id' => $id]);
    }

    public function go(){
	return redirect()->route('name');
	return redirect()->back();
    }
}
```
