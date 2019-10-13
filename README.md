# laravel6-crud-brief-tutorial
Laravel 6 CRUD Brief Tutorial

<ol>
<li>Create a database named "shows"</li>
  <li>create a model by following command
<code>php artisan make:model show-m</code>
</li>
  <li>Previous command will create show.php and [timestamp]create_shows_table.php migration file. go to migration file and add table schema in up method like this<br />
    <code>
      <?php
    public function up()
{
        Schema::create('shows', function (Blueprint $table) {
            $table->bigIncrements('id');
            $table->string('show_name');
            $table->string('genre');
            $table->float('imdb_rating');
            $table->string('lead_actor');
            $table->timestamps();
        });
}
?>
    </code>
    </li>
  
  <li>
Run migration command to add tables to the database
  <code>php artisan migrate</code>

</li>
<li>Inside app/show.php we add fillable properties. These are the properties which can be mass assigned.<br />
<?php

namespace App;

use Illuminate\Database\Eloquent\Model;

class Show extends Model
{
    protected $fillable = ['show_name', 'genre', 'imdb_rating', 'lead_actor'];
}
</li>
<li>
    Now we create a show controller with <code>--resource</code> flag. which will add CRUD methods automatically<br>
    <code>
    php artisan make:controller ShowController --resource
    </code> <br>
    Then we go to routes/web.php and add following <br>
    <code>
<?php
        // ShowController.php

Route::get('/', function () {
    return view('welcome');
});

Route::resource('shows', 'ShowController');
    </code>
    </li>

</ol>
