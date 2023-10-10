# Setup Cypress from scratch
(on ubuntu 20.04) (see https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-20-04)
```
# install dependencies
apt-get install libgtk2.0-0 libgtk-3-0 libgbm-dev libnotify-dev libgconf-2-4 libnss3 libxss1 libasound2 libxtst6 xauth xvfb

#install node and npm (using nvm) (see https://github.com/nvm-sh/nvm)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash

# install node
nvm install lts/hydrogen

# create a new project and install cypress
mkdir cypress
cd cypress

npm init -y
npm install cypress

# check cypress version
npx cypress -v

# open cypress
npx cypress open
```
Merke:  
cypress Tests (Testfiles müssen nach dem Muster <name>.cy.js benannt werden)