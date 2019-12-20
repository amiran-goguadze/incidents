# Incident Management
Powered by SAP Cloud Application Programming Model

## Prerequisites and Setup
1. Get a free trial account on SAP Cloud Platform from https://developers.sap.com/tutorials/hcp-create-trial-account.html
(Follow the provided steps to create your Cloud Foundry space)
2. Install the Cloud Foundry Command Line Interface (CLI) from https://developers.sap.com/tutorials/cp-cf-download-cli.html
(optional: to deploy our local app on CF in the end)
3. Install Visual Studio Code (VS Code) from https://code.visualstudio.com/download
(optional: you can use any IDE such as SAP Web IDE, Eclipe and SAP Cloud Applications Studio)
4. Install Git from https://git-scm.com/downloads
5. Install Node.js from https://nodejs.org
(use latest LTS release)
6. Set npm registry for @sap packages and install cds development kit globally
```sh
npm set @sap:registry=https://npm.sap.com
npm install -g @sap/cds-dk
```

Then:
```sh
git clone https://github.com/amiran-goguadze/incidents.git
cd incidents
npm install
```

## Code & Run
```sh
cds watch
```

Open http://localhost:4004

## Framework generated sql
```sh
cds compile db --to sql
```

## Deploy to SCP's CF environment
```sh
1. cf login
2. cf create-service hanatrial hdi-shared incidents-db-hdi-container
3. npm run build
4. cf push -f gen\db
5. cf push -f gen\srv --random-route 
```

## More
https://cap.cloud.sap/
