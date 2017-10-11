Very Simple VPN Gate Script
===================

Forked from https://github.com/thsteinmetz/vpngate

This is an extremly simple script to connect to a VPN from the vpngate.net service. The script currently only runs on Linux,requires openvpn, and `sudo` in order to run.

Example usage to connect to a specific country (South Korea, in this case):


```php
sudo php vpngate.php -c kr
Attempting to connect to KR - 218.152.74.243...
Connected to KR - 218.152.74.243 successfully.
```

Example usage to check the status of any current VPN connection on the system (this is interactive)

```php
sudo php vpngate.php -c kr -s
VPN is running. Kill it? [y/yes/n/no]: y
VPN is not running. Start one? [y/yes/n/no]: y
Attempting to connect to KR - 218.152.74.243...
Connected to KR - 218.152.74.243 successfully.
```

You can query your current external ip using -i switch. this is useful to see if you are really tunnelled (or still tunnelled)
```php
php vpngate.php -i
Current external ip : 66.16.28.10
```

The -x will download current configuration, parse it and show in human readable format This is helpful to have an overview about current configuration
```php
php vpngate.php -x
.....
64.233.210.239	United States	US	buyer-PC's owner
197.245.118.82	South Africa	ZA	DESKTOP-CMBB1MI's owner
105.159.237.246	Morocco	MA	momm-PC's owner
189.60.65.146	Brazil	BR	COSMOS-II's owner
105.108.8.83	Algeria	DZ	DozKillErZ's owner
Total 151 configurations found from 39 countries
```


You can opt to leave off a country, in that case the script will try the very first VPN in the list.

If the script is unable to connect to a VPN it will continue throughout the list until it runs out of options for either the selected country or every entry returned from the vpngate.net service.
