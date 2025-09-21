# Mom's website

/backup is the pre-any-changes website.
/website-v1 will be the new version God willing.


## Instructions for renewing SSL certificates:
------------
Webspace URL: (where to upload the certificates & http challenge)
- https://cp.a1webhosting.at

<!-- DNS record where to manage the `_acme-challenge.augenarzt-rosenauer.at`
- https://domainmanager.a1.net/dominic-dmw/faces/pages/domainmanage/searchDomain.jsf  -->

------------
SSL renewal:
```bash
# certbot certonly —-manual
# Info: https://certbot.eff.org/instructions?ws=other&os=osx
# sudo certbot certonly --manual --preferred-challenges dns -d augenarzt-rosenauer.at
sudo certbot certonly --manual --preferred-challenges http -d augenarzt-rosenauer.at
```

To view certificates:
```bash
mkdir new_certificates
# sudo cp /etc/letsencrypt/live/augenarzt-rosenauer.at/chain.pem new_certificates/
# sudo cp /etc/letsencrypt/live/augenarzt-rosenauer.at/cert.pem new_certificates/
# sudo cp /etc/letsencrypt/live/augenarzt-rosenauer.at/privkey.pem new_certificates/
# sudo cp /etc/letsencrypt/live/augenarzt-rosenauer.at/fullchain.pem new_certificates/

sudo cat /etc/letsencrypt/live/augenarzt-rosenauer.at/chain.pem
sudo cat /etc/letsencrypt/live/augenarzt-rosenauer.at/cert.pem
sudo cat /etc/letsencrypt/live/augenarzt-rosenauer.at/privkey.pem
```

- chain.pem —> CA-certficate // Privater Schlüssel (*.key) *
- cert.pem —> Certificate // Zertifikat (*.crt) *
- privkey.pem —> Private Key //Privater Schlüssel (*.key) *


Then **Fill out "Erweiterete Settings" > "SSL Zertifikat hinzufugen" Form:**

After that:
Nachdem Sie einer Domain ein SSL/TLS-Zertifikat hinzugefügt haben, müssen Sie die SSL/TLS-Unterstützung aktivieren und das Zertifikat in den Hosting-Einstellungen der Website auswählen: Websites & Domains> Hosting-Einstellungen der Domain> Sicherheit.

```
Websites & Domains > Hosting & DNS > Hosting -> Choose Certificate
```