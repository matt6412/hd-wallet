# High-performance Bitcoin HD Wallet

[![Build Status](https://travis-ci.org/trezor/hd-wallet.svg?branch=master)](https://travis-ci.org/trezor/hd-wallet) [![gitter](https://badges.gitter.im/trezor/community.svg)](https://gitter.im/trezor/community)

For now, mostly a PoC.  Uses
[bitcore-node](https://github.com/bitpay/bitcore-node)
for transaction lookup.

Supports persisting discovered state and doing partial update later on.
Should out-perform all wallets available today that do client-side chain
discovery.

## Example usage

Example is in `example/index.js`; it is compiled in makefile to `gh-pages` directory by `make example`.

Built version is in `gh-pages` branch.

You can also try it yourself here - http://trezor.github.io/hd-wallet/example.html (note that xpubs are preloaded there, but some simple GUI for inputing the XPUBs could be probably done).

## Running regtest tests

Since running the tests require an installed regtest-bitcore *and* an empty regtest blockchain, there is a docker image for that (so you don't litter your system with that)

* `cd docker_test`
* `docker build -t hdwallet_docker_test .`
* `docker run -v /path-to-hd-wallet/hd-wallet:/hd-wallet hdwallet_docker_test bash -c './do.sh && cd /hd-wallet/ && npm run coverage'`
  * or any goal instead of coverage

## License

LGPLv3, (C) 2016 Karel Bilek, Jan Pochyla
