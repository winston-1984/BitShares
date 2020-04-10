Testing BSIP87: Maker / Taker Market Fees

Preface
This document is intended to assist with the testing of maker taker market fees per BSIP 81 Specifications that is available starting in the 4.0.0 Consensus Release.

Testing Introduction
These test instructions should be executed from a command line interface wallet (CLI) that has been built for your test environment. For example, testing performed with the public testnet requires the CLI built for the BitShares Public Testnet. The following instructions were executed on a private testing environment where TEST was the core token. These exact instructions may differ on your test environment in the following ways:

The core token may be different than "TEST" (e.g. "BTS"). Modify the commands to use your core token symbol.
The account names that are created might already exist in your test environment. Check for their existence by running get_account <ACCOUNT_NAME>. Modify the commands to use alternate account names).
The asset names that are created might already exist in your test environment. Check for the existence by running get_asset <ACCOUNT_NAME>.

Testing

    charlie: create an asset MAKER_TOKENS with different 1% maker fee and 2% taker market fee

    charlie: issue assets to bob

    populate alice with TEST core tokens

    alice places limit orders to buy MAKER_TOKENS

    bob places limit order to sell MAKER_TOKENS

    ensure expected results depending upon who is maker vs taker

Initialize the Test Environment

