# dizklosure • ![license](https://img.shields.io/github/license/sambarnes/dizklosure?label=license)

A primitive credentialing system w/ selective disclosure. Written in [noir](https://github.com/noir-lang/noir), a DSL for zk circuits.

The government makes a claim that Alice was born on a given day. This claim, as well as the government's signature covering the claim, is stored off chain.

Bob wants to gate some action on his users being over 21 (i.e. born before a given day, 21 years ago).

With this circuit, Alice can prove the government claims she was born on *some* day before the cutoff, without revealing what day that is.

## Development

To setup the noir toolchain, use [noirup](https://github.com/noir-lang/noirup).

We'll specifically need to use a dev branch, since support for ecdsa over secp256k1 is not yet released.

```bash
noirup --branch aztec3-hacky
```

To test the circuit, use nargo:

```bash
cd circuits
nargo test
```

## TODO

* Fix `nargo prove p` and `nargo verify p`, currently broken here 🤷‍♀️
* Wait for `nargo codegen-verifier` to be fixed with ecdsa sigs
* Integrate foundry into the test framework, building off of [nplate](https://github.com/whitenois3/nplate)

## Disclaimer

_This code is being provided as is. No guarantee, representation or warranty is being made, express or implied, as to the safety or correctness of the user interface or the smart contracts. They have not been audited and as such there can be no assurance they will work as intended, and users may experience delays, failures, errors, omissions, loss of transmitted information or loss of funds. The creators are not liable for any of the foregoing. Users should proceed with caution and use at their own risk._

tl;dr shits barely tested let alone audited -- not for prod
