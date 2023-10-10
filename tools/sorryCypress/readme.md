# Initiales (Full) Setup
Source: https://hub.docker.com/r/agoldis/sorry-cypress-director#docker-images
```
git clone https://github.com/sorry-cypress/sorry-cypress.git

cd sorry-cypress

docker-compose up -f docker-compose.full.yml

# open browser
http://localhost:8080/
```

# Integrating an existing cypress project with sorryCypress
See: https://docs.sorry-cypress.dev/guide/get-started
```
npm install cypress-cloud
```
Create a new configuration file `currents.config.js` in the projects root
```
// currents.config.js
module.exports = {
  projectId: "yyy", // the projectId, can be any values for sorry-cypress users
  recordKey: "xxx", // the record key, can be any value for sorry-cypress users
  cloudServiceUrl: "http://localhost:1234",   // Sorry Cypress users - set the director service URL
};
```
Add cypress-cloud/plugin to cypress.config
```
// cypress.config.js
const { defineConfig } = require("cypress");
const { cloudPlugin } = require("cypress-cloud/plugin");
module.exports = defineConfig({
  e2e: {
    setupNodeEvents(on, config) {
      return cloudPlugin(on, config);
    },
  },
});
```
Tests ausführen (in mehreren Terminals, um zu sehen, dass die Tests parallel laufen)
```
npx cypress-cloud run --parallel --record --key somekey --ci-build-id hello-cypress
```