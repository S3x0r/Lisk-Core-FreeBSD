<h2>Tutorial how to install Lisk Core node on FreeBSD 11.2 amd64</h2>

1. Install tools needed:<br>
pkg install python curl automake libtool git<br>

2. Install node & npm:<br>
pkg install node6 www/npm-node6

3. Install postgresql server:<br>
pkg install postgresql10-server

4. Edit /etc/rc.conf<br>
add line: postgresql_enable="YES"

5. Create user lisk<br>
adduser lisk

6. Configure postgresql<br>
service postgresql initdb<br>
service postgresql start<br>
<br>
su postgres<br>
<br>
createuser -P lisk<br>
createdb lisk_test -O lisk<br>

7. login to lisk account<br>
login lisk

8. Clone Lisk sources:<br>
git clone https://github.com/LiskHQ/lisk.git<br>
cd lisk<br>
git checkout (version) -b (version)<br>
npm install<br>

9. Edit file: node_modules/sc-uws/src/Hub.cpp<br>
comment lines: 128, 130, 131, 132<br>

10. Rebuld modules:<br>
npm rebuild<br>

11. Start node<br>
node app.js --network (network)<br>

Done!
