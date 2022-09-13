# Rustic Finance

## Rustic Frontend 
https://github.com/rustic-finance/frontend

This repository hosts the source code that runs 4 of Rustic Finance's webapps, the landing page, swap page, lending page and webapp. 

## Getting Started

To begin, check your node version. Use node v14.18.1.
```
node -v
```

Install the node dependencies:
```
yarn install
```

The frontend repo is a monorepo. Each package in the monorepo is a [Yarn workspace](https://classic.yarnpkg.com/en/docs/workspaces/). Structuring the repo as a monorepo allows us to share components across multiple webapps.

### Setting up your environment

The webapp uses environment variables to talk to the blockchain. Copy paste these variables and create a new file `webapp/.env`.

You will need to have access to a node to fill up `REACT_APP_MAINNET_URI` and `REACT_APP_TESTNET_URI`, we recommend either [Infura](https://infura.io/) or [Alchemy](https://www.alchemyapi.io/).

In order to switch between the development environment and a production environment, we can change the `REACT_APP_VERCEL_GIT_COMMIT_REF` env var.

```
REACT_APP_VERCEL_GIT_COMMIT_REF=staging # used to see mainnet data

REACT_APP_VERCEL_GIT_COMMIT_REF=development # used to see testnet (kovan) data
```

### Running the webapp

To run the webapp, you need to open two terminals, one in `shared` and another in `webapp`. We
start with running `yarn start` in `shared`.

```
cd shared/
yarn start
```

Now, in the webapp directory, we can start the build server.

```
cd webapp/
yarn start
```

The webapp should automatically open at http://localhost:3000.

### Running the treasury app

To run the treasury app, you need to set the following environment variable

```
REACT_APP_VAULT_COLLECTION=treasury
```

To start building, begin with opening 3 terminal windows:
1. cd `shared`
2. cd `webapp`
3. cd `treasury`

We start with running `yarn start` in `shared`.

```
cd shared/
yarn start
```

Continue with running `yarn lib` in `webapp`.

```
cd webapp/
yarn lib
```


Now, in the treasury directory, we can start the build server.

```
cd treasury/
yarn start
```

The treasury should automatically open at http://localhost:3000. 

## Packages

- `shared`: holds all constants, common React components.
- `landing`: holds the Rustic landing page.
- `webapp`: holds the v1 Rustic webapp.

## Available Scripts

In the individual package directories, you can run:

### `yarn start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### `yarn build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### Local development network
Make sure you select Kovan testnet in Metamask for localhost development.
You can get Kovan testnet Eth from: https://faucet.paradigm.xyz
Kovan testnet was selected because Opyn had their contracts deployed there.

## Contributing

Feel free to open issues and PRs that help improve Rustic's frontend. Rustic's frontend uses the React + Typescript + hooks stack, so experience using these technologies is highly appreciated when making pull requests.

## License

The primary license for rustic-frontend is the Business Source License 1.1 (BUSL-1.1), see LICENSE.
