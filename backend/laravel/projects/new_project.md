# New Project

### Scaffold
Scaffold the new project
`php ./bin/scaffold new [project_name] [project_folder]`

```
php ./vin/scaffold new Timemate /Users/jonrobinson/projects/timemate/backend
```


### Install Vapor
```
composer require laravel/vapor-cli --update-with-dependencies

vapor team:current

composer require laravel/vapor-core --update-with-dependencies
composer require laravel/vapor-ui
php artisan vapor-ui:install
php artisan vendor:publish --tag=vapor-ui-config
```

**Update Vapor Gate: `app/Providers/VaporUiServiceProvider.php`**
```
Gate::define('viewVaporUI', function ($user = null) {
            return $user ? $user->is_admin : false;
        });
```

**Update Composer Script:**
```
{
    "scripts": {
        "post-update-cmd": [
            "@php artisan vapor-ui:publish --ansi"
        ]
    }
}
```


**Zone**
```
vapor zone [your_domain]
```

### Setup Vapor Github Link
1. Go to project
2. Settings
3. Add Github repository

### Setup Github Actions
See Readme.


### Setup Slack Notifications
1. Github Slack Notificaitons
  * Github -> Project -> Settings -> Integrations ->

