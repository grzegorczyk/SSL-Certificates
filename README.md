# SSL-Certificates

Eventually you'll have to give the scripts the right to read/write/execute - this can be done with

```bash
$ chmod 777 mkcert.sh
$ chmod 777 mkssl.sh
```

The provided `sslserverconftxt.txt` lets you skip all the questions usally asked by the ssl certificate generator - you can adjust this to your likings / project, but not really necessary.

### Create an own Certificate Authority

```bash
$ ./mkcert.sh
```
Enter a Common Name, you will need it to installing your root Certificate.<br>
<br>
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

**Drop-In Firefox**

While adding the Root certificate to your keychain provides you with the usage in Chrome and Safari - for Firefox you'll have to add the certificate to the trusted certificates in Firefox itself. This can be done by opening Settings (CMD + ,) and navigating to Privacy & Security - on the bottom of the page you can display the used certificates - do that. You can now import your own certificate and trust it - this way you can use your own SSL certificates also in Firefox for local development.

**Drop-In Firefox**

### Creating CA-Signed Certificate

```bash
$ ./mkssl.sh URL
```
Enter the URL without https://<br>
Enter your passphrase.<br>
The Certificate will be palced in this Repository folder.

**Example**

```bash
$ ./mkssl.sh testing.lcl
```

#### Best usage
Clone this repo in your home directory, this way you'll get a folder named `SSL-Certificates`. You can now use the generated certificates for MAMP or mount this as a volume `/Users/myUser/SSL-Certificates/:/certs/` in Docker.

## Credits
This repo is based on the article published by [Delicious Brains](https://deliciousbrains.com/ssl-certificate-authority-for-local-https-development/).
