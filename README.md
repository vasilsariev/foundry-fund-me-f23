# FundMe Smart Contract

The `FundMe` contract provides a way for users to send funds and for the contract owner to withdraw them. Additionally, this contract uses the Chainlink price feed to ensure a minimum USD amount is funded by the users.

## Features

- Fund the contract with a minimum USD value.
- Get the current version of the price feed.
- Withdraw funds only by the owner.
- Handle the direct ether sent to the contract address.
- View functions for retrieving data about the funders and amounts.

## Dependencies

- Chainlink AggregatorV3Interface: For obtaining the latest ETH/USD conversion rate.
- PriceConverter: A helper library to convert Ether to USD.

## Contract Methods

### `fund()`

Allows a user to fund the contract. Ensures the minimum USD value is maintained.

### `getVersion()`

Returns the current version of the Chainlink price feed.

### `cheaperWithdraw()`

A method to withdraw funds efficiently, clearing the record of funders and their respective amounts. Only accessible by the owner.

### `withdraw()`

Allows the owner to withdraw all funds from the contract.

### `fallback() & receive()`

Handles direct ether sent to the contract address.

### View Functions

- `getAddressToAmountFunded(address)`: Returns the amount funded by a specific address.
- `getFunder(uint256)`: Returns the address of a funder based on their index.
- `getFundersCount()`: Returns the total count of funders.
- `getOwner()`: Returns the address of the owner.

## Installation & Setup

1. Install the Chainlink package:
 ```
 npm install @chainlink/contracts
 ```

2. Deploy the `FundMe` contract by providing the address of the Chainlink price feed contract.

## Notes

Make sure you handle fallback and receive with care, given that they automatically fund the contract.

## License

This project is licensed under the MIT License.

