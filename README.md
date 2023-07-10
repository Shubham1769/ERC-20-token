# ERC-20-token
ERC 20 Token

Introduction: 
The ERC-20 introduces a standard for Fungible Tokens, in other words, they have a property that makes each Token be exactly the same (in type and value) as another Token. For example, an ERC-20 Token acts just like the ETH, meaning that 1 Token is and will always be equal to all the other Tokens.

The ERC-20 (Ethereum Request for Comments 20), proposed by Fabian Vogelsteller in November 2015, is a Token Standard that implements an API for tokens within Smart Contracts.
Example functionalities ERC-20 provides:

1.transfer tokens from one account to another

2.get the current token balance of an account

3.get the total supply of the token available on the network

4.approve whether an amount of token from an account can be spent by a third-party account


detailed explanation of each function in the code:

1. balanceOf :
   - This function takes an `_owner` address as input and returns the token balance of that address.
   - It first checks that the `_owner` address is not the zero address (address(0)). If it is, it reverts with an error.
   - If the address is valid, it retrieves the balance from the `_balances` mapping using the `_owner` address as the key and returns the balance.

2. transfer :
   - This function allows the sender (`msg.sender`) to transfer a specified amount of tokens to another address `_to`.
   - It checks two conditions before proceeding with the transfer:
     - The sender must have a balance greater than or equal to the transfer amount (`_value`).
     - The sender's balance must be greater than zero.
   - If the conditions are met, it deducts the transfer amount from the sender's balance and adds it to the recipient's balance.
   - The function emits a `Transfer` event with the sender's address (`msg.sender`), the recipient's address (`_to`), and the transfer amount (`_value`).
   - Finally, it returns `true` to indicate a successful transfer.

3. transferFrom :
   - This function allows a spender (`msg.sender`) to transfer a specified amount of tokens from the owner's address `_from` to another address `_to`.
   - It requires two conditions to be satisfied before proceeding:
     - The spender must have an allowance (approved tokens) greater than or equal to the transfer amount (`_value`) from the owner.
     - The owner must have a balance greater than or equal to the transfer amount, and the owner's balance must be greater than zero.
   - If the conditions are met, it deducts the transfer amount from the owner's balance and adds it to the recipient's balance.
   - It also deducts the transfer amount from the spender's allowance for the owner.
   - The function emits a `Transfer` event with the owner's address (`_from`), the recipient's address (`_to`), and the transfer amount (`_value`).
   - Finally, it returns `true` to indicate a successful transfer.

4. approve :
   - This function allows the owner (`msg.sender`) to approve a spender (`_spender`) to spend a specified number of tokens (`_value`) on their behalf.
   - It checks that the owner has a balance greater than or equal to the approved amount.
   - If the condition is met, it updates the allowance for the spender in the `_allowances` mapping, using the owner's address as the first key and the spender's address as the second key.
   - The function emits an `Approval` event with the owner's address (`msg.sender`), the spender's address (`_spender`), and the approved amount (`_value`).
   - Finally, it returns `true` to indicate a successful approval.

5. allowance :
   - This function retrieves the current token allowance approved for a spender (`_spender`) to spend on behalf of an owner (`_owner`).
   - It simply returns the value stored in the `_allowances` mapping using the `_spender` address as the first key and the `_owner` address as the second key.

These functions collectively provide the core functionalities required for an ERC20 token contract, including balance queries, token transfers, approvals, and allowance checks.

Deployed Contract Link for easy access for checking:

https://thirdweb.com/contracts/deploy/QmXtHYyASin8BpPRjxzKvfhA5fLo8BbPwV55Kp4nbjL7BC
