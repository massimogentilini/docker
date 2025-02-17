# Italy

This project is configured to download/prepare/build a complete Pelias installation for Italy.

# Setup

Please refer to the instructions at <https://github.com/pelias/docker> in order to install and configure your docker environment.

Given the coverage provided by OpenAddresses is somewhat sparse, it's worth examining the configuration and the OpenAddresses coverage to understand your queries.  

The minimum configuration required in order to run this project are [installing prerequisites](https://github.com/pelias/docker#prerequisites), [install the pelias command](https://github.com/pelias/docker#installing-the-pelias-command) and [configure the environment](https://github.com/pelias/docker#configure-environment).

Please ensure that's all working fine before continuing.

# Differences from other folders
- Enabled port in 5601 for Elastic in docker-compose.yml
- Setup pelias.json with italian data from openaddresses and correct (let's hope) wof record

# Run a Build

To run a complete build, execute the following commands:

```bash
pelias compose pull
pelias elastic start
pelias elastic wait
pelias elastic create
pelias download all
pelias prepare all
pelias import all
pelias compose up
```

# Make an Example Query

You can now make queries against your new Pelias build:

<http://localhost:4000/v1/search?text=Rome>
