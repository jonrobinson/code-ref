### Move Table Column


```
### UNSIGNED ID
DB::statement('ALTER TABLE `task_services_resources` MODIFY COLUMN `status_id`  INT(10) UNSIGNED DEFAULT NULL AFTER `billing_type_id`');
```
