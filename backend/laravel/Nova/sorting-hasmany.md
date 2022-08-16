# Sorting Hasmany
https://github.com/laravel/nova-issues/issues/156
```

public static $orderBy = ['name' => 'asc'];

protected static function applyOrderings($query, array $orderings)
{
    if (empty($orderings) && property_exists(static::class, 'orderBy')) {
        $orderings = static::$orderBy;
    }

    return parent::applyOrderings($query, $orderings);
}
```
