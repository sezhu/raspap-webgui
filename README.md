# `$ robox-wifi-configuration`
RoBox Wifi Configuration -- Forked from raspap-webgui

This project was forked from raspap-webgui. I need a wifi configuration tool for my own product -- RoBox, raspap-webgui would be perfect to fulfill the purpose. However, I need to customize the SSID and UI so that my users can easily understand the web page presented.
I also fixed a few issues on RaspAP that caused problems on my Pi-3
## Contents

 - [Installation](#installation)
 - [Customization](#customization)
 - [License](#license)

## Installation
Install raspap-webgui first (https://github.com/billz/raspap-webgui)

## Customization
1. Change SSID and password:
```sh
sudo nano /etc/hostapd/hostapd.conf
```
* SSID: `RoBoX`
* Password: 20171009

2. Change page title, header, etc.
```sh
sudo nano /var/www/html/index.php
```
```sh
line 67:  <title><?php echo _("RoBox WiFi Configuration Portal"); ?></title>
line 110: <a class="navbar-brand" href="index.php"><?php echo _("RoBox Wifi Portal"); ?></a>
line 180: <img class="logo" src="img/raspAP-logo.png" width="45" height="45">RoBox
```

3. Issues and Fixes
* Issue a. Missing one SSID. See description in https://github.com/billz/raspap-webgui/issues/290
* Fix for a: Comment out line 134 & 136 in configure_client.php

* Issue b. After entered pass-phrase, raspap-webgui wifi got lost.
* Fix for b: Add the following line to configure_client.php

## License
See the [LICENSE](./LICENSE) file.

