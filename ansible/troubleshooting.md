**How to: Fix Vault format unhexlify error OR Vault format unhexlify error: Odd-length string**
```
15:37:11  TASK [Create something] *************************
15:37:12  [WARNING]: There was a vault format error: Vault format unhexlify error: Non-
15:37:12  hexadecimal digit found
15:37:12  fatal: [host]: FAILED! => {"msg": "Vault format unhexlify error: Non-hexadecimal digit found"}
```
Check if there are trailing whitespaces after your ansible-vault credential  

15:45:48  [WARNING]: There was a vault format error: Vault format unhexlify error: Odd-
15:45:48  length string