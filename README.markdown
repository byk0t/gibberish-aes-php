
Gibberish AES, a PHP Implementation
===================================

See Gibberish AES javascript encryption library, [https://github.com/mdp/gibberish-aes](https://github.com/mdp/gibberish-aes)

This class is based on initial code proposed by nbari at dalmp dot com
[http://www.php.net/manual/en/function.openssl-decrypt.php#107210](http://www.php.net/manual/en/function.openssl-decrypt.php#107210)

Live Demo
---------

http://iridadesign.com/starter-public-edition-4/www/playground/gibberish-aes

Requirements:
-----------------------------------

- OpenSSL functions installed and PHP version >= 5.3.3 (the preferred case)

or

- Mcrypt functions installed.

Usage Example:
-----------------------------------

```php
echo '<br />';

// This is a secret pass-phrase, keep it in a safe place and don't loose it.
$pass = 'my secret pass-phrase, it should be long';
echo '$pass = '.$pass;
echo '<br />';
// The string to be encrypted.
$string = 'my secret message';
echo '$string = '.$string;
echo '<br />';
echo '<br />';

// The default key size is 256 bits.
$old_key_size = GibberishAES::size();

echo 'Encryption and decryption using a 256-bit key:';
echo '<br />';
GibberishAES::size(256);
// This is the result after encryption of the given string.
$encrypted_string = GibberishAES::enc($string, $pass);
// This is the result after decryption of the previously encrypted string.
// $decrypted_string == $string (should be).
$decrypted_string = GibberishAES::dec($encrypted_string, $pass);
echo '$encrypted_string = '.$encrypted_string;
echo '<br />';
echo '$decrypted_string = '.$decrypted_string;
echo '<br />';
echo '<br />';

echo 'Encryption and decryption using a 192-bit key:';
echo '<br />';
GibberishAES::size(192);
$encrypted_string = GibberishAES::enc($string, $pass);
$decrypted_string = GibberishAES::dec($encrypted_string, $pass);
echo '$encrypted_string = '.$encrypted_string;
echo '<br />';
echo '$decrypted_string = '.$decrypted_string;
echo '<br />';
echo '<br />';

echo 'Encryption and decryption using a 128-bit key:';
echo '<br />';
GibberishAES::size(128);
$encrypted_string = GibberishAES::enc($string, $pass);
$decrypted_string = GibberishAES::dec($encrypted_string, $pass);
echo '$encrypted_string = '.$encrypted_string;
echo '<br />';
echo '$decrypted_string = '.$decrypted_string;
echo '<br />';
echo '<br />';

// Restore the old key size.
GibberishAES::size($old_key_size);
```

Author: Ivan Tcholakov, 2012-2015.  
License: The MIT License (MIT), [http://opensource.org/licenses/MIT](http://opensource.org/licenses/MIT)

A fragment of code is under the New BSD License, George Argyros, 2012.


## Installation

you can use the library by adding the following snippet to your composer.json

```javascript
{
    "require": {
        "dittertp/gibberish-aes-php" : "1.1.*",
    },
}
```


## running unit-tests
---------

```bash
composer update
vendor/bin/phpunit --bootstrap bootstrap.php --configuration phpunit.xml
```