State Override
--------------

In the process of implementing the move to configuration in core (CMI), most of 
the configuration variables started to be stored in special JSON files. And they
are possible to override from `settings.php` file using 
[the configuration overrides](https://api.backdropcms.org/change-records/any-config-value-can-be-overridden-via-settingsphp)
method.

However, some of the variables weren't found as [actually configuration](https://api.backdropcms.org/change-records/statekey-value-storage-system-implemented) 
and they started to be stored in specially implemented states storage system. Unlike configuration variables the "state" varriables are used for saving long-term 
values in the database that are environment-specific. Examples of some "state" 
varaibles are:

    cron_key
    cron_last
    css_js_query_string
    install_task
    install_time
    maintenance_mode

This small utility module makes it possible to override the "state" variables in 
the same manner the configuration variables can be overriden from the `settings.php` file.
It is especially useful, for example, if you need to sync databases between 
environments which at the same time must be in different maintenance mode.

Installation
------------

- Install and enable State Override module using the official Backdrop CMS instructions at
https://backdropcms.org/user-guide/modules; 
- Alternatively use [Brush](https://backdropcms.org/project/brush) and get it downloaded,
installed and enabled with a single CLI command `brush -y en state_override`.

Usage
-----

Open the file `settings.php` and add your state overrides like so:

```
$config['state']['maintenance_mode'] = TRUE;
$config['state']['cron_key'] = 'w5AXKo9UdkoVRp9rT_0gqtdG2h322LGJ_sYuJN6aWpk1';
```

Credits and current Maintainers
-------------------

- Created and maintained by [Alan Mels](https://github.com/alanmels)

License
-------

This project is GPL v3 software.
See the LICENSE.txt file in this directory for the complete text.
