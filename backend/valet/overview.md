# Valet Overview 

### Change PHP version
```
valet use php@7.4
```

### Link a folder to a website name
(e.g, link theavenue.test to the backend folder)
```
valet link theavenue
```


### Fix PHP Reference Error

First stop the php instance with Brew
```
sudo brew services stop php@X.X
```

Restart with desired PHP version
```
brew services restart php
```



### Fix PHP Reference Error (Option 2)
```
brew install php@7.4
brew link --force --overwrite php@7.4
brew services start php@7.4
export PATH="/usr/local/opt/php@7.4/bin:$PATH"
export PATH="/usr/local/opt/php@7.4/sbin:$PATH"
```
