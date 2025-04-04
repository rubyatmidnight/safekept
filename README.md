# SafeKept

A multi-signature wallet with time-lock features for harm-reduction focused funds management. 

This wallet implements a 2-of-3 multi-signature setup with:

Key 1. A user key that you control

Key 2. A time-locked key that is used for faucet functions

Key 3. A backup key that is provided after the holding period, and allows the wallet to be freely accessed

## What is a multi-sig wallet?

A multi-signature wallet is a cryptocurrency wallet, in this instance available in Litecoin (LTC) and Bitcoin (BTC), which requires more than one authorized 'key' to move funds out of the wallet. For instance, A group of 4 people could use a multisig wallet as a business fund, where a majority need to approve to access the funds. 

For our purposes, we will be automating the 2nd and 3rd keys, and putting them on a time release schedule based on the configured input. Because this doesn't require the use of anyone else's obfuscated systems, we can also implement features like security levels (to make it more or less 'forgiving' if the user decides to back out) and auto-faucets pointed towards a static address.

You have key 1, and when applicable, the wallet will automatically provide a hashed version of key 2. The third key will be given at the end of the time lock duration.

## How much will this cost?

The desktop version is free, and will remain free. However, a donation option is available on an optional menu screen. 

In the future, I may charge a small up-front amount for a fully featured mobile app, but there will always be a version available for free, if less configurable. 

### Important: DO NOT USE A TRON (TRX/TRC20) MULTISIG WALLET FOR ANY PURPOSE LIKE THIS!!!

TRX multisig wallets work differently: there is a 'parent' wallet which can still access and move the funds, while anyone can deposit into the wallet, even if someone has 'access', they are unable to do anything with it, while the malicious remote owner could access it and withdraw it to any account at will.

We want to use multi-sig in its pure form, where several authentications are needed to access the funds, while the blockchain lets us easily see and ensure that our funds are still safe and untouched. 

## How is this safer than letting a friend hold my crypto?

By making a new wallet every time using the proper libraries,

	- NO outside users or 'bank'/'trust' is needed, and everything can be done locally. 
	- There are NO fees or costs to doing this; harm reduction should be encouraged, and not taxed.  
	- ALL operations are transparent and visible, and the code is open source
	- All created wallets are non-custodial, and after the time lock, YOU have access to the private keys.  

## I'm not very technical, what are possible problems?

Because we are using fully non-custodial and time-locked non-interactable wallets, *IF YOU SOMEHOW PERMANENTLY LOSE BOTH KEY 1 AND 3*, you cannot access the wallet anymore, and any funds inside are lost forever. 

## Functionality

1. **Setup**: Create a wallet with a specified time-lock duration (e.g., 30 days)
2. **Deposit**: Funds sent to the wallet address require 2 of 3 signatures to spend
3. **Spending**: Initially, only the combination of user key + time-lock key allows spending
4. **Recovery**: After the time-lock expires, the backup key becomes available, as well as the seed phrase. 
5. **Faucet**: Configurable periodic withdrawals of a percentage of your total deposit

# Installation

TBD

## ~ Usage ~

TBD

## Limitations

- 

## License

MIT
