## Migrations

**Migrations create table**

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

```php
Schema::create('categories', function (Blueprint $table) {
    $table->string('slug');
});
```