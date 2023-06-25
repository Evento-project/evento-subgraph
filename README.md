From Unlock Protocol Using [The Graph](https://thegraph.com).

### Building the subgraph

```sh
# create correct ABIs and config files
yarn prepare

# generate graph code from source
yarn codegen

# build Web Assemly binaries
yarn build <network-name>
```

### Config

#### Multiple chains 

Learning how Unlock team works.

There is subgraph deployed for each network where Unlock Protocol is deployed. While code is similar for all, the addresses where the contracts are deployed vary, requiring a specifying config per network stored in `networks.json`.

The `networks.json` file is generated from our `@unlock-protocol/networks` package.

```sh
# build the `subgraph.yaml` with the correct contract address per network
yarn prepare:networks
```

### Deploying The Subgraph

Deploy the latest subgraph code to the graph node.

```sh
export SUBGRAPH_DEPLOY_KEY=<api-key>

# build
yarn run build <network-name>

# deploy a single network
yarn run deploy <network-name>

# deploy all networks
yarn run deploy-all
```

## Tests

(preferred way) Run the tests using Docker

```
yarn test -d
```

Run coverage

```
yarn test -d -c
```

## Helpers

Show all events from different contract versions.

```sh
yarn show-events
```

## Add to the subgraph

To add a particular property to the subgraph you need to

1. add to schema
2. edit the mappings
3. test it
4. republish the new subgraph
