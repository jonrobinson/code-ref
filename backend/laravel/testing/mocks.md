# Mocking


### Mocking w/ Class Ouside Of Handler
Note: Use `overload:`
```php
$this->mock('overload:Twilio\Security\RequestValidator', function ($mock) {
    $mock->shouldReceive('validate')
        ->andReturn(true)
        ->once();
});
```
