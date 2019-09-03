nishtman/sms
======
This library helps developers to easily call the web services of sms providers in Iran using the Larval Framework.

## Supported providers
- [MeliPayamak](http://melipayamak.ir "MeliPayamak")
- [HostIranSms](http://sms.hostiran.ir "HostIranSms")
- [sms.ir](http://sms.ir "sms.ir")

## Installation

#### Requirements:
- `php >= 7.0`
- `laravel >= 5.0`

Run the Composer update command

    $ composer require nishtman/sms

- First, enter the settings for your short message provider in the `config/sms.php` file and enter the module name you want in the `default` section.

<a name="basic-usage"></a>
## Usage
### Basic usage

Sending sms
```php
public function send()
{
	/*
	* Instance the sms object
	*/
	$sms = new \Nishtman\Sms\Sms();
	$result = $sms->send('09123456789', 'text message');
	/*
	* or you can use facades
	*/
	$result = Nishtman\Sms\Facades\Sms::send('09123456789', 'text message');
}
```
### Selecting provider
```php
public function send()
{
        /*
         * Instance the sms object
         */
        $sms = new \Nishtman\Sms\Sms();
        $result = $sms->provider('HostIran')->send('09123456789', 'text message')
        /*
         * or you can use facades
         */
        $result = Nishtman\Sms\Facades\Sms::provider('HostIran')->send('09123456789', 'text message');
}
```
