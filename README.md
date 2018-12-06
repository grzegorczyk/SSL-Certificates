# SSL-Certificates

### Create a Certificate Authority

```bash
$ ./mkcert.sh
```

Enter pass phrase for myCA.key. You will need the pass phrase later to create Certificates.

### Installing Your Root Certificate

<ol>
<li>Open the macOS Keychain</li>
<li>File > Import Items</li>
<li>Select root certificate file (myCA.pem)</li>
<li>Search the your Common Name</li>
<li>Double click on your root certificate</li>
<li>Expand the Trust section</li>
<li>Change the When using this certificate: select box to “Always Trust”</li>
</ol>

### Creating CA-Signed Certificate

```bash
$ ./mkssl.sh URL
```

Example

```bash
$ ./mkssl.sh testing.lcl
```
