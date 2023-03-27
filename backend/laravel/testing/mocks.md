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


### You might need to add this to the test to get tests working
https://stackoverflow.com/questions/51708289/mockery-fails-with-could-not-load-mock-class-already-exists-when-running-w
```
/**
 * @runInSeparateProcess
 * @preserveGlobalState disabled
```
