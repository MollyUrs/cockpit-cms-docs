# Cockpit CMS Docs (Unofficial)
I love using Cockpit CMS, but the official documentation isn't great, especially for the PHP SDK that's built in. In fact there's no mention of it at all in the docs. This documentation will help you understand how to use the built in SDK. Feel free to contribute.

## Introduction
To get started, it's quite simple. All we need is to require the `bootstrap.php` file located in the root of the cockpit admin directory.

```php
<?php 
require 'admin/bootstrap.php';
?>
```
Next, I'll show you some very basic but fundamental ways of accessing singleton and collection data using this SDK that we just required.
```php
<?php
require 'admin/bootstrap.php';

// Finds all entries in the 'blog' collection.
$blog = cockpit('collections')->find('blog');

// Gets singleton data from 'settings' singleton.
$settings = cockpit('singletons')->getData('settings');
```

The data returned is in the form of an associative array. It's returned in the same way that the HTTP API would return data (after using json_decode). As you can see using this SDK is far quicker than using the HTTP API. I haven't ran any benchmarks but I can fairly confidently only assume that its more performant.
