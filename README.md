# poma's ez guide to running an eth2 validator node

- Install [docker](https://docs.docker.com/engine/install/) and [docker-compose](https://docs.docker.com/compose/install/)
- Download docker-compose.yml from this repo: `git clone https://github.com/poma/eth2node && cd eth2node`
- (optional) change infura token in `docker-compose.yml`
- Copy your `validator_keys` directory generated during eth2 deposit to the current dir
- Import the validator keys into your node `docker-compose run --rm lighthouse_validator lighthouse account validator import --directory /validator_keys`
- Run the beacon and validator with `docker-compose up -d`
- Look at logs with `docker-compose logs -f`
- Done

## Using your own geth node

If you want to use your own geth look into `docker-compose.yml` and uncomment the relevant lines, change your `eth1-endpoint` accordingly. Please note that geth sync can take quite a while (1-2 days).

## Next steps

Now you'll probably want set up monitoring and stuff. Check out [Lighthouse docs](https://lighthouse-book.sigmaprime.io) for that.
