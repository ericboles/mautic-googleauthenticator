# Mautic Google Authenticator

A Mautic plugin for two-step verification login with Google Authenticator.


### Prerequisites

* Mautic 6.0+ or Mautic 7.0+
* Project was originally built for Mautic 5.0.2
* This fork includes compatibility fixes for Mautic 6/7 (Symfony 6)

### Installing

Clone repo.

```sh
$ git clone <repo-url>
```

For development symlink the plugin, to plugins directory.

```sh
cd <mautic-root>/plugins
ln -s <repo-root-folder>HostnetAuthBundle .
```

Clear the cache & reload

```sh
cd <mautic-root>
rm -rf var/cache/dev/* var/cache/prod/*
php bin/console mautic:plugins:reload --env=dev
```

### Coding style & Syntax Check

Use Mautic core style fixer/checker (composer fixcs) .

## Deployment

Download this project as a zip file and extract the content from the zip file.

Copy the **HostnetAuthBundle** folder to the **plugins** folder of your Mautic installation.

Clear the cache running this command from the Mautic main folder:

```sh
$ rm -rf var/cache/prod/*
```

Reload the plugins:

```sh
$ php bi/console mautic:plugins:reload --env=prod
```

( Alternatively you can access the plugins page in the Mautic panel and click on **Install/Update Plugins**.)

### Activation and Usage

Once the plugin is installed you will need to activate it. Select the Google Authenticator on the plugins page and turn the **Published** option to **Yes**.

To use this integration you need to install the **Google Authenticator** app on your phone and scan the QR Code that appears on the plugin settings page.

Once you've done that, when you log into your Mautic you'll be requested to enter a token that you can get on your app.

In the options you can set how many days you wish to not enter the code again when you set a browser as trusted.

## Changelog

### Mautic 6/7 Compatibility (dev_mautic5 branch)
* Fixed `RequestEvent::isMasterRequest()` deprecated method → `isMainRequest()`
* Removed `SessionInterface` from Integration constructor (no longer supported in Symfony 6)
* Updated session access pattern from `$this->get('session')` to `$request->getSession()`
* Fixed DateTime instantiation to use objects instead of date strings
* Restructured plugin directory for proper Mautic integration

## Built With

* [Mautic](hhttps://github.com/mautic/mautic) - Marketing Automation Tool
* [Composer](https://getcomposer.org/) - Dependency Management

## Contributing

Any contributions are welcome.

## Versioning

[todo]

## Authors

Este plugin é mantido pela empresa Hostnet Hospedagem de Sites, esperamos que seja útil para você.

A Hostnet oferece diversas soluções mais aprimoradas para a utilização do Mautic, seja no modo "faça você mesmo", ou com todo o ambiente gerenciado por nós.

Saiba mais nos links:  
https://www.hostnet.com.br/hospedagem-de-sites/  
https://www.hostnet.com.br/mautic-automacao-marketing/

***

This plugin is developed by Hostnet Web Hosting, we hope it will be useful for you.

Hostnet offers many and more enhanced solutions for using Mautic, both in "do it yourself" mode or with the whole environment managed by us.

Learn more at:  
https://www.hostnet.com.br/hospedagem-de-sites/  
https://www.hostnet.com.br/mautic-automacao-marketing/



