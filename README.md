# vsftpd
vsftpd conf for OpenSUSE
To Install vsftpd on OpenSUSE

zypper in vsftpd

# save /etc/vsftpd.conf
cp /etc/vsftpd.conf /etc/vsftpd.conf.orig

# alter logins.txt with the users e password you needed
(Requires the Berkeley db program installed).
zypper in db-utils
db_load -T -t hash -f logins.txt /etc/vsftpd_login.db

# Create virtual user
useradd -d /srv/ftp virtual

# Copy files in this repository to /etc and /etc/pam.d
# Restart vsftpd
systemctl enable vsftpd
systemctl restart vsftpd


(Requires the Berkeley db program installed).
zypper in db-utils
