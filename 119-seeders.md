## Auth

- Yeni bir seeder oluşturmak için `php artisan make:seeder RoleTableSeeder`

- RoleTableSeeder içerisinde çoklu kayıtlarımızı yapalım;
```php
public function run()
{
    $roles = [
        ['title' => 'admin'],
        ['title' => 'writer'],
        ['title' => 'guest'],
    ];

    foreach ($roles as $role) {
        Role::create($role);
    }
}
```

- DatabaseSeeder içerisinde ekleyelim;
```php
public function run()
{
    $this->call(RoleTableSeeder::class);
}
```

- Seederları çalıştırmak için; `php artisan db:seed`