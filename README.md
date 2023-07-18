# Logical Gate Circuit Implementation

This repository contains the implementation of a logical gate circuit using the Circom programming language. The circuit implements a logic gate that takes two inputs, A and B, and produces an output based on the following condition: A (0) and B (1) yield a 0 output.

## Contents

- `circuit.circom`: This file contains the implementation of the logical gate circuit using the Circom language. It defines the inputs, outputs, and the constraints that enforce the desired behavior of the logic gate.
- `compile.js`: This script is used to compile the circuit and generate the necessary intermediaries for proving the correctness of the circuit.
- `prove.js`: This script generates a proof using the inputs A=0 and B=1. It uses the compiled circuit and the provided inputs to create a proof of correctness.
- `verifier.sol`: This Solidity contract defines a verifier that can be deployed to the Goerli Testnet. The verifier contract has a method `verifyProof` that takes a proof as input and returns a boolean value indicating whether the proof is valid or not.
- `deploy.js`: This script deploys the verifier contract to the Goerli Testnet.
- `test.js`: This script interacts with the deployed verifier contract by calling the `verifyProof` method with a proof and asserts that the output is true.

## Usage

0. Delete the MyCircuitVerifier.sol present in the contracts folder to successfully compile the circuit.  

1. Install the necessary dependencies by running `npm install`.

2. Compile the circuit by running `npx hardhat circom`. This command will generate the intermediaries needed for proving the correctness of the circuit.

3. Deploy the verifier contract to the Goerli Testnet by running `npx hardhat run scripts/deploy.ts --network goerli`. 

4. This command will deploy the verifier contract and provide you with the contract address.
   Generate a proof using the inputs A=0 and B=1 by running `generateProof()`.
   Generates calldata with `generateCallData()`
   Calls `verifyProof()` on the verifier contract with calldata.
   This command will interact with the deployed verifier contract and assert that the output of the `verifyProof` method is true.

## Authors

RIDAM ADITYA SINHA

https://www.linkedin.com/in/ridam-sinha-188133210/

ridamsinha20@gmail.com

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgements

This project was created as part of a challenge and utilizes the following tools and resources:

- Circom programming language: [https://github.com/iden3/circom](https://github.com/iden3/circom)
- Hardhat-Circom template: [https://github.com/cristianbrumat/hardhat-circom](https://github.com/cristianbrumat/hardhat-circom)
- Solidity: [https://docs.soliditylang.org](https://docs.soliditylang.org)
- OpenZeppelin Contracts: [https://docs.openzeppelin.com/contracts](https://docs.openzeppelin.com/contracts)

Please refer to the respective documentation and repositories for more information on these tools.
