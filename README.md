# Reactable for Laravel 5.x

Easy to use reactions like Slack for your Laravel models, without pain.

## Installation

Go to your project's root folder and composer require

    $ cd projects/project
    $ composer require muratbsts/laravel-reactable dev-master

Add the service provider to config/app.php file:

```php
<?php
...
'providers' => [
    ...
    Muratbsts\MailTemplate\Providers\ReactableServiceProvider::class,
    ...
],
...
```

## Usage

Use package as like below in your models

```php

// Post model
use Muratbsts\Reactable\Traits\Reactable;

class Post extends Model
{
    use Reactable;
    ...
    ...
}


// User model
use Muratbsts\Reactable\Traits\Reactor;

class User extends Model
{
    use Reactor;
    ...
    ...
}
```

And do make some reactions as like below

```php

# Get an user's reactions
User::find(1)->reactions()->get();

# Get an post's reactions
Post::find(1)->reactions()->get();

# Make a reaction with Reactor
Post::find(1)->reaction('claps', User::find(1)); // Reaction, Reactor

# Or with Reactable
User::find(1)->reaction('claps', Post::find(1)); // Reaction, Reactable
```

🎉 Cheers! That's it!

## License

[MIT](./LICENSE) © [Murat Bastas](http://muratbt.com)
