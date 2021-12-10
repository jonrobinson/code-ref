# Updating Homestead


### Remove Current Virtual Machine
```
vagrant destroy
```

### Update Homestead Source Code
```
git fetch
git pull origin release
```

### Update Vagrant Box
```
vagrant box update
```

### Bash Init To Update Configuration Files
```
bash init.sh
```

### Regenerate Homestead Virtual Machine
```
vagrant up
```

