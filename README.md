# LibreTranslate-init
[Demo](https://translate.argosopentech.com) | [Video tutorial](https://www.youtube.com/watch?v=mwacU-yqJwc) | [Video tutorial 2](https://www.youtube.com/watch?v=SJ8lNcn4cjE)

[LibreTranslate](https://libretranslate.com) install scripts for Ubuntu

Uses [LibreTranslate WSGI](https://community.libretranslate.com/t/is-wsgi-currently-supported/24/3) with [Gunicorn and Nginx](https://www.digitalocean.com/community/tutorials/how-to-serve-flask-applications-with-gunicorn-and-nginx-on-ubuntu-18-04).

```
# Add libretranslate user
useradd libretranslate
mkdir /home/libretranslate
chown libretranslate:libretranslate /home/libretranslate
usermod -aG sudo libretranslate
passwd -d libretranslate
su libretranslate

# Download LibreTranslate-init
git clone https://github.com/argosopentech/LibreTranslate-init.git ~/LibreTranslate-init

# Download dependencies and run LibreTranslate on port 5000
~/LibreTranslate-init/setup.sh

# Run LibreTranslate WSGI with nginx and systemd
~/LibreTranslate-init/run.sh

# Check LibreTranslate status
sudo systemctl status libretranslate

# Enable https
~/LibreTranslate-init/get-cert.sh

```

