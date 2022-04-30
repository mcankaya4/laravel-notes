## Form İşlemleri

**ADD FORM**

- $categories dizisindeki kategoriler selectbox'ta listeleniyor.

```html

<form method="post" action="{{route('panel.post.add.store')}}" enctype="multipart/form-data">
    @csrf
    <div class="form-group">
        <input type="file" name="img">
    </div>
    <div class="form-group">
        <input type="text" class="form-control" name="title">
    </div>
    <div class="form-group">
        <select class="form-control" name="category_id">
            @foreach($categories as $category)
            <option value="{{$category->id}}">
                {{$category->title}}
            </option>
            @endforeach
        </select>
    </div>
    <div class="form-group">
        <textarea name="blog_content" rows="5"></textarea>
    </div>
    <div class="form-group">
        <button type="submit" name="submit" class="btn btn-primary">Kaydet</button>
    </div>
</form>
```

- Önceden seçili olan kategoriye selected attr eklemek.

```html
<select class="form-control" name="category_id">
    @foreach($categories as $category)
    <option value="{{$category->id}}" {{ $post->category_id == $category->id ? 'selected' : null }} >
        {{$category->title}}
    </option>
    @endforeach
</select>
```

**FILE UPLOAD**

- Form'a `enctype="multipart/form-data"` ifadesi eklenmeli.
- Her hangi bir resim seçilip seçilmediğini anlamak için;

```php
if (!$request->img) {
    return redirect()->route('/');
}
```

- Eğer seçili resim var ise uzantısını ve name değerini değişkene atalım;

```php
$extension = $request->img->getClientOriginalExtension();
$basename = $request->img->getClientOriginalName();
```

- Belirlenen uzantılar dışında bir dosya seçilmiş kontrolu yapalım.

```php
if (!($extension === "jpeg") && !($extension === "png") && !($extension === "jpg")) {
    return redirect()->route('/');
}
```

- Dosyayı public/asset/img/ dizini içerisine kayıt edelim.
- Basename değerini random bir değer oluşturarak verebiliriz.

```php
$request->img->move(public_path('asset/img'),$basename);
```

- Şimdide bu dosyanın yolunu db'ye kayıt edelim.

```php
Post::create([
    'img' => $basename,
]);
```






