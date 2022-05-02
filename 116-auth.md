## Auth

- Auth işlemleri için [laravel breeze](https://laravel.com/docs/9.x/starter-kits#laravel-breeze-installation) paketini kullanacağız.
- Öncelikle kurulum işlemlerini gerçekleştiriyoruz.

- Kullanıcı girişi yapmak için; 
```php
Auth::attempt([
    'email' => 'mcankaya4@gmail.com',
    'password' => '123123123'
    ], true);
```

- Model ile kullanıcı girişide yapılabilir; `Auth::login(User::find(1));`
- Giriş yapan kullanıcı bilgilerine ulaşmak için; `Auth::user();`
- Çıkış yapmak için; `Auth::logout();`
- Login oldu mu diye sorgulamak için; `Auth::check();`
- Misafir mi diye sorgulamak için; `Auth::guest();`
- Beni hatırla seçeneği aktif mi sorgusu için; `Auth::viaRemember();`

