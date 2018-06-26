## GraphQL Security
Enabling this module will hide entity_owner from graphql results by default

### How to extend the module to hide more fields
1. Debug the supported GraphQL fields via [graphql_security.module](./graphql_security.module) and uncomment 
```php
\Drupal::service('logger.factory')->get('php')->error('<pre>' . var_dump($fields['entity_owner']) . '</pre>');
```  
2. Go to drupal and clear the cache. Clearing the cache will force GraphQL to reconstruct it's schema. Thus executing 
the line above
3. Once you identify the field name/type. just remove it from the fields array
4. Be happy 😁