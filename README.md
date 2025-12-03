# Electrum Sweeper
A utility to automatically sweep funds from private key BTC wallets to another address using Electrum.
I made this tool to forward the balance of vanity BTC addresses to a main BTC wallet, but I am sure there are other uses for it.
This tool works on **Linux & macOS only** as the Windows Electrum wallet does not have a CLI interface.

## Installation
Download and install the Electrum BTC wallet from [Electrum.org](https://electrum.org/#download). Make note of where the Electrum binary is installed, as you will need to point Electrum Sweeper at it (or add the location to path).

## Usage
Create a text file with one BTC private key and one BTC address on each line, separated by a |
```
p2pkh:notreallyaprivatekey|myotherbtcaddres
p2pkh:anotherprivatekey|mysecondbtcaddress
```
Build Electrum Sweeper, then use it from the CLI. In this example, Electrum is added to path, so there is no need to provide the full path to the binary. The delay is how often, in seconds, the program will check your private keys for balance.
```
./electrum_sweeper --delay 10 --key_file keys.txt --path electrum
```
To enable and disable logging, use the q/quiet and v/verbose arguments
```
./electrum_sweeper --delay 10 --key_file keys.txt --path electrum -vvvvv  // very loud
./electrum_sweeper --delay 10 --key_file keys.txt --path electrum -q  // totally quiet
```
