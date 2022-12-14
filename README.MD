# HTTPS ON LIVE SERVER VSCODE.

### GENERATE THE CRT AND KEY WITH OPEN SSL
##### put inside of your keys folder and then 
```ssl
openssl genrsa -aes256 -out clave.key 2048
```
##### use the path of your openssl instalation folder 
```ssl
openssl req -new -x509 -config "C:\Program Files\OpenSSL\bin\openssl.cnf" -sha256 -key clave.key -out certificado.crt -days 365
```

### THEN
Go to your visual code project.
Create .vscode folder inside the project. 
Inside that folder create settings.json file.
Paste the following code:

```json
{
    "liveServer.settings.https": {
        "enable": true, //set it true to enable
        "cert": "G:\\_JAVASCRIPT\\API CAMARA JS\\keys\\certificado.crt", //full path of the certificate
        "key": "G:\\_JAVASCRIPT\\API CAMARA JS\\keys\\clave.key", //full path of the private key
        "passphrase": "123456"
    }
}
```

