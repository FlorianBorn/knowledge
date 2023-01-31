**How to: Decrypt secrets via commandline and ansible-vault**
```
echo '<$ANSIBLE_VAULT;1.1;AES256 ... my-secret>' | ansible-vault decrypt
```