# Tailwind Form

## About

I use [Laravelcollective](https://laravelcollective.com/ "Laravel Collective's Homepage") lib HTML and [Tailwind](http://tailwindcss.com/ "Tailwind's Homepage")

I wanted a easy way to use both together,

If you want to, you can replace with this library.

## Installation

Edit your ``config/app.php`` and add thoses lines :

##### providers
```php
TomJamon\TailwindLaravel\TailwindLaravelServiceProvider::class,
```

##### aliases
```php
'Form' => TomJamon\TailwindLaravel\FormFacade::class,
'Html' => TomJamon\TailwindLaravel\HtmlFacade::class,
```    
        
## Custom components

Publish vendor views : ``php artisan vendor:publish``

Choose : ``Provider: TomJamon\TailwindLaravel\TailwindLaravelServiceProvider``

A new folder ``resources/views/vendor/tailwindlaravel`` will be created with every components.

You can now change every components class and stuff.

## Examples

##### Simple text input 

```php
{!! Form::control('text', 'name', $errors, [
    'label' => 'Nom Prenom',
    'placeholder' => 'John Doe',
    'md' => '1/2'
]) !!}
```

##### Textarea with data

```php
{!! Form::control('select', 'type', $errors, [
    'label' => 'Type',
    'message' => 'La page a un format different d\'un article',
    'data' => [
        'one' => 'First choice', 
        'two' => 'Second choice', 
        'three' => 'Third choice'
    ]
]) !!}
```

##### Textarea with overrided rows number (Second array arguments)

```php
{!! Form::control('textarea', 'content', $errors, [
    'label' => 'Contenu',
    'placeholder' => 'Contenu du post',
], [
    'rows' => '25'
]) !!}
```

## Why use : Clarity and simplicity

Here is how a form can look like, with an IDE allowing to regroup array

##### Login form

```php
{!! Form::open(['route' => 'frontend.login']) !!}
    {!! Form::control('text', 'email', $errors, [...],  [...]) !!}
    {!! Form::control('password', 'password', $errors, [...]) !!}
    {!! Form::control('checkbox', 'remember', $errors, [...], [...]) !!}
    {!! Form::submit('Sign in') !!}
{!! Form::close() !!}
```
                        
 