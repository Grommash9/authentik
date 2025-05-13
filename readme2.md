sudo apt-get install python3.13-dev
sudo apt-get install libgss-dev krb5-config libkrb5-dev postgresql-server-dev-all
sudo apt-get install libxml2-dev libxslt1-dev
sudo apt-get install libxmlsec1-dev pkg-config

make install

make gen-client-ts

make gen-dev-config

nvm install 20
nvm use 20

make web-build

docker build -t authentik-with-uk:2025.4.0.9 .
docker tag authentik-with-uk:2025.4.0.9 prudnikov21/authentik-with-uk:2025.4.0.9
docker push prudnikov21/authentik-with-uk:2025.4.0.9