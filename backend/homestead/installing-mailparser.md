### Installing PHP MailParser



### PHP 7.4
```
sudo apt-get update -y
sudo apt-get install -y php7.4-mailparse
```
IMPORTANT: Mailparser must come after `mbstring.ini` in the config list
To ensure this change the numbering to be later.

```
cd /etc/php/7.4/cli/conf.d
sudo mv 20-mailparse.ini 25-mailparse.ini
```



### PHP 8
```
sudo apt-get update -y
sudo apt-get install -y php-mailparse
```

