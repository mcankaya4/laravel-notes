## Validation

**Controller**

```php
public function store(Request $request)
{
    $validate = $request->validate(
        [
            'title' => 'required|max:3',
            'img' => 'mimes:jpg,jpeg,png',
            'category_id' => 'integer'
        ],
        [
            'title.required' => 'Title değeri boş bırakılamaz',
            'title.max' => 'Title değeri 3 karakterden fazla içeremez',
            'img.mimes' => 'Dosya sadece jpg, png, jpeg formatlarında olabilir',
            'category_id.integer' => 'Kategori değeri sayı olmak zorundadır'
        ]
    );
}
```

- Eğer validate'e uygun değilse view'e geri döner.
- View'de hatayı $errors ile alabiliriz.

**View**

```php
@if ($errors->any())
    {{ dd($errors->all()) }}
@endif
```

