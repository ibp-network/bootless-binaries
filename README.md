# sterile-binaries
This repository holds bootnode-sterilised versions of polkadot, cumulus and encointer binaries

## Confirm sterile

To confirm that the binaries are really sterile, try them first without specifying any bootnodes, for example, to try the polkadot relaychain:

```shell
polkadot-sterile --no-hardware-benchmarks --no-mdns --chain polkadot
```

and it should show something similar to the following entries once the initialization messages are completed:

```
2023-05-16 11:45:14 💤 Idle (0 peers), best: #0 (0x6c9e…b1b3), finalized #0 (0x6c9e…b1b3), ⬇ 0 ⬆ 0
2023-05-16 11:45:19 💤 Idle (0 peers), best: #0 (0x6c9e…b1b3), finalized #0 (0x6c9e…b1b3), ⬇ 0 ⬆ 0
2023-05-16 11:45:24 💤 Idle (0 peers), best: #0 (0x6c9e…b1b3), finalized #0 (0x6c9e…b1b3), ⬇ 0 ⬆ 0
2023-05-16 11:45:29 💤 Idle (0 peers), best: #0 (0x6c9e…b1b3), finalized #0 (0x6c9e…b1b3), ⬇ 0 ⬆ 0
```

## Test bootnode

Once satisfied with the results, it is time to use the sterilised binary to test the subject bootnode:

```shell
polkadot-sterile --no-hardware-benchmarks --no-mdns --chain polkadot --bootnodes "/dns/dot-bootnode-cr.gatotech.network/tcp/31310/p2p/12D3KooWK4E16jKk9nRhvC4RfrDVgcZzExg8Q3Q2G7ABUUitks1w"
```
This time, the node should start discovering peers and syncing the blockchain, like this:

```
2023-05-16 11:50:23 ⚙️  Syncing, target=#15546630 (8 peers), best: #44596 (0x8b4d…71cf), finalized #44544 (0x6d9a…d1be), ⬇ 267.6kiB/s ⬆ 9.6kiB/s
2023-05-16 11:50:28 ⚙️  Syncing 605.4 bps, target=#15546630 (13 peers), best: #47623 (0x687c…f02d), finalized #47616 (0x1c2b…2c58), ⬇ 270.9kiB/s ⬆ 5.4kiB/s
2023-05-16 11:50:33 ⚙️  Syncing 613.0 bps, target=#15546630 (16 peers), best: #50688 (0x266e…7787), finalized #50176 (0xa61b…30ee), ⬇ 228.8kiB/s ⬆ 9.1kiB/s
2023-05-16 11:50:38 ⚙️  Syncing 601.2 bps, target=#15546631 (20 peers), best: #53694 (0x545c…e54f), finalized #53248 (0x0b21…f0b0), ⬇ 194.1kiB/s ⬆ 2.2kiB/s
```

Enjoy!
