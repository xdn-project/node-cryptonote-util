Node-Cryptonote-Util
====================

Adding merged mining with ringCT support to DigitalNote to be used with crpytonote-universal-pool.  Note: this compiles but does not work with cryptnote-universal-pool yet, not sure sure where the mistakes are.

I referenced DigitalNote fork changes (https://github.com/xdn-project/digitalnote/commit/7a321b7a85d41263f33c35c6c69d9a1256d677db and https://github.com/xdn-project/digitalnote/commit/6f53611c3e635e31f33ec0b7ab8dc90263edc214) in coordination with the ringCT upgrades (https://github.com/zone117x/node-cryptonote-util/commit/b3d5e4305238d7cfc6fa860f289851e4d08be771) but in the form of the XDN block structure as per Jan 9, 2017 updates https://github.com/xdn-project/digitalnote/commit/6f53611c3e635e31f33ec0b7ab8dc90263edc214.  I attempted to create a new class called "parent_block_transaction" to act as the ringCT carrier, I also updated all references to the major version (which is now 4) and the transaction version (which is now 2).  The code seems to line up correctly but I am not sure what I am doing wrong...below is the current readout when I run init.js with this code:

/root/xdnclone/node_modules/cryptonote-util/node_modules/bindings/bindings.js:83
        throw e
              ^
Error: /root/xdnclone/node_modules/cryptonote-util/build/Release/cryptonote.node: undefined symbol: _ZTVN10cryptonote24parent_block_transactionE
    at Module.load (module.js:356:32)
    at Function.Module._load (module.js:312:12)
    at Module.require (module.js:364:17)
    at require (module.js:380:17)
    at bindings (/root/xdnclone/node_modules/cryptonote-util/node_modules/bindings/bindings.js:76:44)
    at Object.<anonymous> (/root/xdnclone/node_modules/cryptonote-util/index.js:1:99)
    at Module._compile (module.js:456:26)
    at Object.Module._extensions..js (module.js:474:10)
    at Module.load (module.js:356:32)
    at Function.Module._load (module.js:312:12)

I do not know anything about node js so I don't know if there is a mistake in my implementation of ringct support for merge-mined blocks, or if there is something that now needs to be updated with cryptonote-universal-pool.
