using vim to read manpage
```
export MANPAGER="vim -M +MANPAGER -"
```


find serial port plugin
```
ls /dev/ > dev_list_1.txt
ls /dev/ | diff --suppress-common-lines -y - dev_list_1.txt
```

```
lspci -i | grep -i "vga"
```