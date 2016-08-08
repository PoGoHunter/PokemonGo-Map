Ubuntu 16.04 deploy
===================
apt-get update
apt-get upgrade
apt-get install python-pip nodejs npm nodejs-legacy node-gyp node-sass python-dev libpython-dev libevent-dev aptitude libc6-dev python-setuptools gcc
git clone https://github.com/PoGoHunter/PokemonGo-Map.git
git checkout develop
pip install --upgrade pip
pip install -r requirements.txt
npm install --unsafe-perm


SSL certifications
==================
apt-get install python-openssl letsencrypt
letsencrypt certonly --standalone -d FQD_NAME.TLD
cp /etc/letsencrypt/live/FQD_NAME.TLD/cert.pem ./cert.pem
cat /etc/letsencrypt/live/FQD_NAME.TLD/chain.pem >> ./cert.pem
cp /etc/letsencrypt/live/FQD_NAME.TLD/privkey.pem ./key.pem
pip install Flask-SSLify
pip install pyOpenSSL

