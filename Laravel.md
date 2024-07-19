# Tes notes sur Laravel

- API : Une API (application programming interface ou « interface de programmation d'application ») est une interface logicielle qui permet de « connecter » un logiciel ou un service à un autre logiciel ou service afin d'échanger des données et des fonctionnalités.

- API REST : Une API REST est une interface de programmation d'application (API) qui permet d'établir une communication entre plusieurs logiciels. Grâce à elle, des logiciels d'applications utilisant différents systèmes d'exploitation peuvent interagir et partager des informations par l'intermédiaire du protocole HTTP.

- MVC (Modele vue controleur)  Modèle-vue-contrôleur ou MVC est un design patterns destiné aux interfaces graphiques, lancé en 1978 et très populaire pour les applications web. 

    Modele : Element qui contient des données ainsi que la logique en rapport avec les données 
    Vue : c'est la partie visible de l'interface graphique 
    Controleur : Module qui traite les actions de l'utilisateur, modifie les données du modèle et de la vue.

![MVC](./image/Modèle-vue-contrôleur_(MVC)_-_fr.png)

## Creer des routes 
    Une route sert à créer une URL pour acceder à des pages
```php
- Route::get('/customer', [CustomerController::class, 'customershow'] );
```
## Controller 
Un controlleur  permet de remplir une route 
```php
- class CustomerController extends Controller
{
    public function customershowid(string $id):object
    {
        return response()->json([
            'id'=>$id,
            'name'=>'Don diego',

            ]

        );
    }
}
```
## Models
Sert à relier une BDD à son API
```php
class User extends Model
{
    use HasFactory;
    /**
     * Get the comments for the blog post.
     */

    /**
     * The table associated with the model.
     *
     * @var string
     */

    protected $table = 'users';

    protected $fillable = ["first_name","last_name", "email", "password","civility","adress","city","phone_number"];



```

## Migrations
Sert à créer des tables
```php
 public function up(): void
    {
        Schema::create('users', function (Blueprint $table) {
            $table->id()->primary();
            $table->string('first_name');
            $table->string('last_name');
            $table->string('email');
            $table->string('password');
            $table->string('civility');
            $table->string('adress');
            $table->string('city');
            $table->string('phone_number');
            $table->timestamps();
        });
    }

```


## Seeders
Sert à remplir nos tables
```php
class seederusers extends Seeder
{
    /**
     * Seed the application's database.
     */
    public function run(): void
    {
        for ($i = 0; $i < 10 ; $i++)
        {
            // User::factory(10)->create();
            DB::table('users')->insert([
                'first_name' => Str::random(10),
                'last_name' => Str::random(10),
                'email' => Str::random(10) . '@gmail.com',
                'password' => Str::random(15),
                'civility' => Str::random(3),
                'adress' => Str::random(15),
                'city' => Str::random(15),
                'phone_number' => Str('0102030405'),
            ]);
        }
    }
}

```
