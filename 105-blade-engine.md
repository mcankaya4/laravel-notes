## Blade Engine

**Master layout sistemi oluşturmak;**

- `master.blade.php` taslak page

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Starter</title>

    <link rel="stylesheet" href="{{asset('asset/dist/css/adminlte.min.css')}}">
    @yield('css-in')
</head>
<body>

<div class="container">
    @yield('content')
</div>

<script src="{{asset('asset/plugins/jquery/jquery.min.js')}}"></script>
@yield('js-in')

</body>
</html>
```

- `index.blade.php` index page

```php
@extends('panel.layouts.master')

@section('css-in')
    // css
@endsection

@section('js-in')
    // js
@endsection

@section('content')
    // content
@endsection
```