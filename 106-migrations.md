## Migrations

**Migrations create table**

- users adında table oluşturur.

`php artisan make:migration create_user_table --create=user`

```php
Schema::create('categories', function (Blueprint $table) {
    $table->id();
    $table->string('title')->unique();
    $table->bigInteger('parent_id')->unsigned();
    $table->text('desc')->nullable();
    $table->enum('status',[0,1,2]);
    $table->integer('child_id');
    $table->boolean('status');
    $table->timestamps();
});
```

**Migrations add column**

- users table içerisinde yeni column oluşturur.

`php artisan make:migration add_new_column_user --table=user`

```php
Schema::create('categories', function (Blueprint $table) {
    $table->string('slug');
});
```