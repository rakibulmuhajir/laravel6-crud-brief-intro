# laravel6-crud-brief-tutorial
Laravel 6 CRUD Brief Tutorial

<ol>
<li>Create a database named "shows"</li>
  <li>create a model by following command
<code>php artisan make:model show-m</code>
</li>
  <li>Previous command will create show.php and [timestamp]create_shows_table.php migration file. go to migration file and add table schema in up method like this
    <code>
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
    </code>
    </li>
  
  <li>
Run migration command to add tables to the database
  <code>php artisan migrate</code>

</li>
</ol>
