Testing BSIP87: Maker / Taker Market Fees

Preface
This document is intended to assist with the testing of maker taker market fees per BSIP 81 Specifications that is available starting in the 4.0.0 Consensus Release.

Testing Introduction
These test instructions should be executed from a command line interface wallet (CLI) that has been built for your test environment. For example, testing performed with the public testnet requires the CLI built for the BitShares Public Testnet. The following instructions were executed on a private testing environment where TEST was the core token. These exact instructions may differ on your test environment in the following ways:

The core token may be different than "TEST" (e.g. "BTS"). Modify the commands to use your core token symbol.
The account names that are created might already exist in your test environment. Check for their existence by running get_account <ACCOUNT_NAME>. Modify the commands to use alternate account names).
The asset names that are created might already exist in your test environment. Check for the existence by running get_asset <ACCOUNT_NAME>.

Testing

    bob and alice create assets and issue them to charlie and daniel

    charlie and daniel place opposing limit orders which fill

    ensure expected results depending upon who is maker vs taker
    
Scenario

In BitShares, you pay the fee upon **receiving an asset**, suppose:

bob, owner of bob_UIA sets:

    Maker fee for bob_UIA market at 0.1%
    Taker fee for bob_UIA market at 0.2%

alice, owner of alice_UIA set:

    Maker fee for alice_UIA market at 0.3%
    Taker fee for alice_UIA market at 0.4%

charlie places a limit order to buy (receive) `bob_UIA` with payment of `alice_UIA` onto the order book.

daniel, fills charlie's order by selling `bob_UIA` to receive `alice_UIA` immediately.

    charlie is a `bob_UIA:alice_UIA` market **Maker**
      charlie *recieves* `bob_UIA`
	    charlie pays bob 0.1%


In BitShares, You pay the fee upon **receiving an asset**. Hence, one	

    daniel is a **Taker** in the `bob_UIA:alice_UIA` market
      daniel *receives* `alice_UIA`
	    daniel pays alice 0.4% 
	    
Test where:

    charlie is the buying maker
    charlie is the selling maker
    charlie is the buying taker
    charlie is the selling taker

Initialize the Test Environment

