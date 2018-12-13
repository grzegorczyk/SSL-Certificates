# SSL-Certificates

### Create an own Certificate Authority

```bash
$ ./mkcert.sh
```
Enter a Common Name, you will need it to installing your root Certificate.

Enter a passphrase for myCA.key (myCA is now your own Certificate Authority). You will need the passphrase later to create Certificates.

### Installing your root Certificate

<ol>
<li>Open the macOS Keychain</li>
<li>File > Import Items</li>
<li>Select your root Certificate file (myCA.pem)</li>
<li>Search your Common Name</li>
<li>Double click on your root Certificate</li>
<li>Expand the Trust section (DE: Vertrauen)</li>
<li>Change the "When using this certificate:" select box to “Always Trust” (DE: Bei Verwendung dieses Zertifikats: Immer vertrauen)</li>
</ol>

### Creating CA-Signed Certificate

```bash
$ ./mkssl.sh URL
```
Enter the URL without https://
Enter your passphrase.
The Certificate will be palced in this Repository folder.

# Example

```bash
$ ./mkssl.sh testing.lcl
```
