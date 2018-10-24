# Lisk-Core-FreeBSD

Tutorial how to install Lisk Core node on FreeBSD 11.2 amd64


1. Install tools needed:
pkg install python curl automake libtool git

2. Install node & npm:
pkg install node6 www/npm-node6

3. Install postgresql server:
pkg install postgresql10-server

4. Edit /etc/rc.conf
add line: postgresql_enable="YES"

5. Create user lisk
adduser lisk

6. Configure postgresql
service postgresql initdb
service postgresql start

su postgres

createuser -P lisk
createdb lisk_test -O lisk

7. login to lisk account
login lisk

8. Clone Lisk sources:
git clone https://github.com/LiskHQ/lisk.git
cd lisk
git checkout (version) -b (version)
npm install

9. Edit file: node_modules/sc-uws/src/Hub.cpp
comment lines: 128, 130, 131, 132

10. Rebuld modules:
npm rebuild

11. Start node
node app.js --network (network)
