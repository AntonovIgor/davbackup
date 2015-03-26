DavBackup 1.0.0
===============

Creating backup sites in the clouds through WebDav


## Requirements
* PHP version 5.3.6 or higher

### Supported clouds
* `Yandex Disk`
* `CloudMe`
* `GoogleDrive` working through service [dav-pocket](https://dav-pocket.appspot.com/)
* `DropBox` working through service [dropdav](https://www.dropdav.com/)
* ~~`Mail Disk`~~ temporary does not work
* ~~`OneDrive`~~ temporary does not work

### Example of work
```php
require 'DavBackup.php';

$ya = new YandexBackup('test@yandex.ru', 'test');
$ya->db('user', 'password', 'db');
$ya->folder('/var/www/public_html/');
$ya->backup();
```
### Example add WebDav cloud
```php
class MyDavBackup extends DavBackup
{
    const URL = 'https://dav.my.ru/';

    public function __construct($login, $password)
    {
        parent::__construct(self::URL, (string) $login, (string) $password);
    }
}
```