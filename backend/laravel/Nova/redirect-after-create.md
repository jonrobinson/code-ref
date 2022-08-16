# Redirect After Create
```
/**
 * Return the location to redirect the user after creation.
 *
 * @param  \Laravel\Nova\Http\Requests\NovaRequest  $request
 * @param  \Laravel\Nova\Resource  $resource
 * @return \Laravel\Nova\URL|string
 */
public static function redirectAfterCreate(NovaRequest $request, $resource)
{
    return '/resources/'.static::uriKey().'/'.$resource->getKey();
}
```


### Redirect (Internally) After Action
https://nova.laravel.com/docs/3.0/actions/defining-actions.html#action-responses
```
return Action::push('/resources/posts/new', [
  'viaResource' => 'users',
  'viaResourceId' => 1,
  'viaRelationship' => 'posts'
]);
```


