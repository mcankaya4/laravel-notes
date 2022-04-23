## Artisan Komutları

**1- Route**

Tüm route listesini görmek için

`php artisan route:list`

**2- Controller**

Controller oluşturmak için;

`php artisan make:controller UserController`

İçerisinde crud işlemleri için methodlar tanımlanmış controller oluşturmak için;

`php artisan make:controller UserController --resource`

**2- Migration**

Table oluşturmak için;

- users adında table oluşturur.

`php artisan make:migration create_user_table --create=user`

Table içerisinde yeni bir column oluşturmak için;

- users table içerisinde yeni column oluşturur.

`php artisan make:migration add_new_column_user --table=user`

Table ve Column'ları migrate etmek için;

`php artisan migrate`

Migrate durumlarını görmek için;

`php artisan migrate:status`

Son migrate işlemini geri almak için;

`php artisan migrate:rollback`

- rollback işleminde hata alırsak `composer dump-autoload` komutunu çalıştırmamız yeterli olacaktır.

Tüm table ve column'ları geri alıp tekrar migrate etmek için;

`php artisan migrate:refresh`

**3- Model**

Model oluşturmak için;

- User adında model oluşturur.

`php artisan make:model User`

Model, migration, controller, factory, seeders oluşturmak için;

`php artisan make:model User -mcfs --resource`
