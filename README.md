# OpenCart

## Overview

OpenCart is a free open source ecommerce platform for online merchants. OpenCart provides a professional and reliable foundation from which to build a successful online store.

## Info

- Bug fixes added
- Support PHP 7.0 and above
- OpenBay was removed
- Integrated Currency module from Master Branch - 3.1.0.0b
- Integrated Timezone from Master Branch - 3.1.0.0b
- Added Show/Hide password. Code used from <a href="https://github.com/opencartbrasil/opencartbrasil">Opencart Brasil</a>
- Integrated Cron module from Master Branch - 3.1.0.0b
- Added vendor folder for some payments
- Bootstrap 3.4.1
- jQuery 3.5.1


## Language patch for non English

For Currency module and Timezone

- Edit admin/language/your_language/setting.php and add this values:

$_['entry_timezone']               = 'Time Zone';\
$_['entry_currency_engine']        = 'Currency Rate Engine';

- Copy currency.php from admin/language/en-gb/extension/extension in the same location of your language.
- Copy currency folder from admin/language/en-gb/extension/ in the same location of your language.

For Cron module

- Edit admin/language/your_language/column_left.php and add this value:

$_['text_cron']                      = 'Cron Jobs';

- Copy cron.php from admin/language/en-gb/extension in the same location of your language.

## Patching standard version of Opencart 2.3.0.2

Cron Module

- If you had standard Opencart 2.3.0.2 and you have replaced with this version then you need to create in Database "oc_cron" table from opencart.sql

Admin config

Replace old structure

// DIR<br>
define('DIR_APPLICATION', '/your_path/admin/');<br>
define('DIR_SYSTEM', '/your_path/system/');<br>
define('DIR_LANGUAGE', '/your_path/admin/language/');<br>
define('DIR_TEMPLATE', '/your_path/admin/view/template/');<br>
define('DIR_CONFIG', '/your_path/system/config/');<br>
define('DIR_IMAGE', '/your_path/image/');<br>
define('DIR_CACHE', '/your_path/system/storage/cache/');<br>
define('DIR_DOWNLOAD', '/your_path/system/storage/download/');<br>
define('DIR_LOGS', '/your_path/system/storage/logs/');<br>
define('DIR_MODIFICATION', '/your_path/system/storage/modification/');<br>
define('DIR_UPLOAD', '/your_path/system/storage/upload/');<br>
define('DIR_CATALOG', '/your_path/catalog/');<br>

With the new one

// DIR<br>
define('DIR_APPLICATION', '/your_path/admin/');<br>
define('DIR_SYSTEM', '/your_path/system/');<br>
define('DIR_IMAGE', '/your_path/image/');<br>
define('DIR_STORAGE', DIR_SYSTEM . 'storage/');<br>
define('DIR_CATALOG', '/your_path/catalog/');<br>
define('DIR_LANGUAGE', DIR_APPLICATION . 'language/');<br>
define('DIR_TEMPLATE', DIR_APPLICATION . 'view/template/');<br>
define('DIR_CONFIG', DIR_SYSTEM . 'config/');<br>
define('DIR_CACHE', DIR_STORAGE . 'cache/');<br>
define('DIR_DOWNLOAD', DIR_STORAGE . 'download/');<br>
define('DIR_LOGS', DIR_STORAGE . 'logs/');<br>
define('DIR_MODIFICATION', DIR_STORAGE . 'modification/');<br>
define('DIR_SESSION', DIR_STORAGE . 'session/');<br>
define('DIR_UPLOAD', DIR_STORAGE . 'upload/');<br>

Catalog config

Replace old structure

// DIR<br>
define('DIR_APPLICATION', '/your_path/catalog/');<br>
define('DIR_SYSTEM', '/your_path/system/');<br>
define('DIR_LANGUAGE', '/your_path/catalog/language/');<br>
define('DIR_TEMPLATE', '/your_path/catalog/view/theme/');<br>
define('DIR_CONFIG', '/your_path/system/config/');<br>
define('DIR_IMAGE', '/your_path/image/');<br>
define('DIR_CACHE', '/your_path/system/storage/cache/');<br>
define('DIR_DOWNLOAD', '/your_path/system/storage/download/');<br>
define('DIR_LOGS', '/your_path/system/storage/logs/');<br>
define('DIR_MODIFICATION', '/your_path/system/storage/modification/');<br>
define('DIR_UPLOAD', '/your_path/system/storage/upload/');<br>

With the new one

// DIR<br>
define('DIR_APPLICATION', '/your_path/catalog/');<br>
define('DIR_SYSTEM', '/your_path/system/');<br>
define('DIR_IMAGE', '/your_path/image/');<br>
define('DIR_STORAGE', DIR_SYSTEM . 'storage/');<br>
define('DIR_LANGUAGE', DIR_APPLICATION . 'language/');<br>
define('DIR_TEMPLATE', DIR_APPLICATION . 'view/theme/');<br>
define('DIR_CONFIG', DIR_SYSTEM . 'config/');<br>
define('DIR_CACHE', DIR_STORAGE . 'cache/');<br>
define('DIR_DOWNLOAD', DIR_STORAGE . 'download/');<br>
define('DIR_LOGS', DIR_STORAGE . 'logs/');<br>
define('DIR_MODIFICATION', DIR_STORAGE . 'modification/');<br>
define('DIR_SESSION', DIR_STORAGE . 'session/');<br>
define('DIR_UPLOAD', DIR_STORAGE . 'upload/');<br>