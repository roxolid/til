# Converting PPK to PEM keys

You will need to install `putty` package from repository.

Then use `puttygen` command:
```
$ puttygen private_key_from_putty.ppk -O private-openssh -o private_key_for_openssh.pem
```

To convert in opposite direction:
```
$ puttygen pemKey.pem -O private -o ppkKey.ppk
```
