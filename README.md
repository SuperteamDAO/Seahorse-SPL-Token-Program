This project was created by Seahorse 0.2.5.

# Seahorse Token Program
The Objective of this project is to create a **Lottery smart contract** where users can buy lottery tickets and a random winner will be selected from all participants and lottery prize will be rewarded to the winner.

## Prerequisites
We need to install some command line tools for this project to build. We need [Solana](https://docs.solana.com/cli/install-solana-cli-tools), [Anchor](https://project-serum.github.io/anchor/getting-started/installation.html#install-rust), [NodeJS](https://nodejs.org/en/) and [Seahorse](https://seahorse-lang.org/docs/installation). The links provided contain the step-by-step guide on installing these tools and the dependencies required for them like Rust.

You can check if package got installed correctly by running command like :

`solana -V`
`anchor -V`
`seahorse -V`

For this project, the version used are :
* anchor 0.25.0

* seahorse v0.2.5

* node 19.0.0

## Getting started with Seahorse
We initialize Seahorse Project using command `seahorse init token_program`. This will create a project directory with multiple files which is mostly similar to anchor projects, just will write our seahorse program in `token_program/programs_py/token_program.py`

## Involved Accounts
There are 2 types of accounts involved here, which are **TokenMint** and **TokenAccount**. The Manager is responsible for creating the Lottery and its parameters like lottery price and calling the random winner from all lottery buyers. On the other hand, Users are the people who are buying the lottery. 


## Program Instructions
We have 4 functions/instructions in this Program. Let's understand all the different Program instructions one by one.

### 1. initTokenMint
When someone wants to create a new token, we have to use something create-token function to initialize a new Mint Account. `initTokenMint` is the function where we create our TokenMint Accounts. TokenMint account contains the following informations: `mint-authority` which is a public-key (pubkey) authorized to mint this token,the number of `decimals` of the token etc. This account stores general information about the token and who has permissions over it. Observe that there is no data about token holdings of particular individuals. These are stored in Token Accounts.



