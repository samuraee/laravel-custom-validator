Laravel 5+ Custom Validators
============

Installation
-------
```
composer require "tartan/laravel-custom-validator"
```

Tartan Custom Validators
-------------------------
Add the required validator(s) to boot method of `app/Providers/AppServiceProvider.php`
 
```php
 Validator::extend('strength', 'Tartan\CustomValidator\Validators@validateStrength');
 Validator::extend('iran_billing_id', 'Tartan\CustomValidator\Validators@validateIranBillingId');
 Validator::extend('iran_shetab_card', 'Tartan\CustomValidator\Validators@validateShetabCard');
 Validator::extend('uuid', 'Tartan\CustomValidator\Validators@validateUuid');
 Validator::extend('iran_national_id', 'Tartan\CustomValidator\Validators@validateNationalId');
```

Add following lines to `resources/lang/en/validation.php` in `Custom Validation Language Lines` part

```php
'strength' => 'The password :attribute is too weak and must contain one or more uppercase, lowercase, numeric, and special character (!@#$%^&*).',
'iran_billing_id' => 'The billing Id `:attribute` is not a valid Billing Id.',
'shetab_card' => 'The card number `:attribute` is not a valid Shetab card number.',
'uuid' => 'The UUID `:attribute` is not a valid UUID.',
'iran_national_id' => 'The national id `:attribute` is not a valid Iran nationa Id.',
```

Use like other validator

```php
	...
	'national_id'    => 'required|iran_national_id|unique:users,national_id',
	'password'       => 'required|string|strength|min:6'
	...
```

## Team

This component is developed by the following person(s) and a bunch of [awesome contributors](https://github.com/theTartancoder/laravel-custom-validator/graphs/contributors).

[![Aboozar Ghaffari](https://avatars1.githubusercontent.com/u/502961?s=200&v=4)](https://github.com/iamtartan) |
--- |
[Aboozar Ghaffari](https://github.com/theTartancoder) |

## Support This Project
  
[![Donate via Paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=LXEL22GFTXTKN)

## License

The Laravel Custom Validator is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)
