# Kognito

## Dynamic Rule System (DRS)
 
It assembles, store and recall JSON-encoded 'backpack configurations'. It receives a unique, validated user and a target platform as an input and return a customized JSON array 'backpack configuration' (the JSON configuration file that our front end uses to populate a course library) as output.
 
### Requirements
 
DRS uses a number of open source projects to work properly:
 
* [Composer] - ```v1.6.*``` - Tool for dependency management in PHP.
* [Laravel] - ```v5.4.*``` - PHP Framework For Web Artisans.
* [MySQL] - ```v5.7.*``` - RDBMS for web application software stacks.
* [PHP] - ```v7.0.*``` - Server-side scripting language designed for web development.
* [Vue.js] - ```v2.0.*``` - JavaScript framework for building user interfaces.
 
### Installation
The actual ```.env``` file(s) are under ```.../configuration/XXX/.env``` folder
 
    XXX --> might be development / production / qa
- change or create ```.env``` file with below mentioned attributes,
    - APP_URL
    - DB_HOST
    - DB_PORT
    - DB_DATABASE
    - DB_USERNAME
    - DB_PASSWORD
 
Run below commands before running Server
 
```shell
    > composer install
    > php artisan migrate
    > php artisan db:seed
```
 
- Give executable permission for ```storage``` folder
 
### Running Server
 
```shell
    > php artisan serve
```
 
### Unit Testing
 
    $> vendor/bin/phpUnit tests/Unit
    $> vendor/bin/phpUnit tests/Feature
 
### DRS API
 
- Kognito library to get data assembled in templates
 
Endpoint :
 
http://{HOSTNAME}/happiest-minds-snap/server.php/api/library
 
Input Type : RAW JSON
 
_This function is used for API Authentication._
 
#### JSON Parameters:
 
| name | Type | required | description |
| --- | --- | --- | --- |
| userId | \*integer | required | userId |
| platform | \*string | required | platform |
 
**example** :
 
{&quot;userId&quot;: 1,&quot;platform&quot;: &quot;web&quot;}
 
#### Output Parameters:
 
| name | Type | description |
| --- | --- | --- |
|   | JSON | JSJSON Response |
 
**example** :
 
{ &quot;status&quot;: true, &quot;data&quot;: { &quot;1&quot;: { &quot;library&quot;: { &quot;categories&quot;: [] }, &quot;sim-menu&quot;: { &quot;bundles&quot;: {}, &quot;courses&quot;: { &quot;hello&quot;: &quot;hi&quot; }, &quot;modules&quot;: [], &quot;categories&quot;: { &quot;id&quot;: &quot;ctv2\_convo\_thumb\_breastfeeding&quot;, &quot;path&quot;: &quot;ctv2/texture-bundles/ctv2\_convo\_thumb\_breastfeeding&quot;, &quot;local&quot;: false, &quot;version&quot;: 1, &quot;useUrlPrefix&quot;: true, &quot;keepBundleDuringRescan&quot;: false } } } } }
