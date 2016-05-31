# fb
facebook login v1

first you must download this cert file to work fine !

cert, just in case you have a new one

https://github.com/bagder/ca-bundle/blob/e9175fec5d0c4d42de24ed6d84a06d504d5e5a09/ca-bundle.crt

Put it somewhere. In my case that was if you use wamp put it here c:\wamp\ or xampp  here c:\xampp\  directory.

Enable mod_ssl in apache and php_openssl.dll in php.ini. But be carefull, 
two php.ini files and I need to do this in both of them

Also add paths to your cert in both of these php.ini files:

curl.cainfo="C:/wamp/ca-bundle.crt"
openssl.cafile="C:/wamp/ca-bundle.crt"


============================================

another steps

steps worked. Basically a change in the cacert.pem file. Hope this helps someone.

Download cacert.pem file from here: http://curl.haxx.se/docs/caextract.html
Save the file in your PHP installation folder. (eg: If using xampp – save it in c:\Installation_Dir\xampp\php\cacert.pem).
Open your php.ini file and add these lines:
curl.cainfo=”C:\Installation_Dir\xampp\php\cacert.pem” openssl.cafile=”C:\Installation_Dir\xampp\php\cacert.pem”
Restart your Apache server and that should fix it (Simply stop and start the services as needed).
