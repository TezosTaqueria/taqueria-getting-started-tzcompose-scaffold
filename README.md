# Getting Started with TzCompose and Taqueria

This scaffold is a Taqueria project that demonstrates how to use TzCompose to automate your deployment pipelines with Taqueria. TzCompose is a powerful tool that allows you to define and execute complex workflows using simple YAML configurations.

## Project Overview

This project focuses on deploying two contracts authored in LIGO, which you will find in the **contracts/** directory:

1. **Increment**: A permissioned version of a contract that maintains an internal counter. The counter can be incremented or decremented using the provided entrypoints. This contract delegates permission checks to members of the Membership contract.

2. **Membership**: A contract that represents a membership system. Users can join the group by paying 1 tez.

## TzCompose Configuration

The project comes pre-installed with the `@taqueria/plugin-tzcompose` package and includes a `tzcompose.yaml` file. You can execute the pipelines defined in this file using the command `taq run tzcompose.yaml`.

The provided pipeline accomplishes the following:

1. Deploy both contracts to the current Taqueria environment. By default, the environment is set to a Flextesa sandbox. Before executing the pipeline, make sure to run `taq start sandbox`, unless you've adjusted the environment configuration to deploy to a testnet or mainnet. The _Increment_ contract will have a dependency on the _Manager_ contract.
2. Add Bob as a member in the _Manager_ contract.
3. As Bob, call the _increment_ entrypoint on the _Increment_ contract, demonstrating that Bob has permissioned access.
4. As Alice, call the _increment_ entrypoint on the _Increment_ contract, which will fail and demonstrate that Alice does NOT have permissioned access.

## TzCompose: Automating Workflows on Tezos

TzCompose is a versatile tool that simplifies the automation of various workflows on the Tezos blockchain. It allows you to write YAML files to configure pipelines consisting of different tasks, which can be executed with a single command across all Tezos networks. TzCompose even supports cloning contracts and transaction sequences between networks.

Some common use cases for TzCompose include:

- Smart contract deployment and maintenance
- Traffic generation for protocol and application testing
- Test-case setups
- Cloning contract deployments and setup logic between networks

Whether you're a dapp developer, protocol engineer, generative artist, or any other enthusiast building on Tezos, TzCompose will greatly streamline your development process.

## Available Tasks in TzCompose

TzCompose pipelines define a list of tasks that are processed in order, with each task producing a transaction. Some of the available tasks include:

- `batch`: Send multiple transactions as a single operation
- `call`: Send a smart contract call
- `delegate`: Delegate to a baker
- `deploy`: Create a smart contract
- `double_endorse`: Force a double endorsement slash
- `register_baker`: Register as a baker
- `token_approve`: Approve a token spender
- `token_revoke`: Revoke a token spender
- `token_transfer`: Send token transfer(s)
- `transfer`: Send tez transfer(s)
- `undelegate`: Remove delegation from a baker
- `wait`: Wait for a condition

For more information on TzCompose and its usage, please refer to the official documentation.

## Getting Started

To get started with this scaffold project:

1. Create a project based on this scaffold: `taq new getting-started-tzcompose`
4. Start the Flextesa sandbox by running `taq start sandbox`.
5. Execute the TzCompose pipeline by running `taq run tzcompose.yaml`.

Feel free to explore the project structure, modify the contracts, and experiment with different TzCompose configurations to suit your needs.

We hope this scaffold project serves as a helpful starting point for your Taqueria and TzCompose journey!
