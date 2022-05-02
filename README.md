The virhost script creates a virtual host on an apache development server. It's invoked like this:

```virhost mywebsite```

It makes sure that the "/etc/apache2/sites-available" directory exists, that the user provided a name, and that no virtual host file by that name already exists. Then it makes an appropriately named copy of the default configuration file, and changes its contents so that it becomes the new website's configuration file. The file is then activated and the apache2 process is reloaded/started.

For example, if the user provides the name "mywebsite", the new configuration file will be named "mywebsite.conf" and its settings will be:

	ServerAdmin webmaster@mywebsite.com
	DocumentRoot /var/www/mywebsite
	ServerName mywebsite.com

Of course, the script can be easily edited if you wish to make more/different changes; just make the necessary adjustments to the sed command and you're good to go ;-)
