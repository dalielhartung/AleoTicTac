<<<<<<< HEAD
<!-- # ⭕ Tic-Tac-Toe -->

[//]: # (<img alt="workshop/tictactoe" width="1412" src="../.resources/tictactoe.png">)

A standard game of Tic-Tac-Toe in Leo.

⭕ ❕ ⭕ ❕ ❌

➖ ➕ ➖ ➕ ➖

⭕ ❕ ⁣❌ ❕ ⭕

➖ ➕ ➖ ➕ ➖

❌ ❕ ❌ ❕ ⭕

## Representing State
Leo allows users to define composite data types with the `struct` keyword. 
The game board is represented by a struct called `Board`, which contains three `Row`s.
An alternative representation would be to use an array, however, these are not yet supported in Leo.

## Language Features
- `struct` declarations
- conditional statements
- early termination. Leo allows users to return from a function early using the `return` keyword.

## Running the Program

Leo provides users with a command line interface for compiling and running Leo programs.
Users may either specify input values via the command line or provide an input file in `inputs/`.

### Providing inputs via the command line.
1. Run 
```bash
leo run <function_name> <input_1> <input_2> ...
```
See `./run.sh` for an example.


### Using an input file.
1. Modify `inputs/tictactoe.in` with the desired inputs.
2. Run
```bash
leo run <function_name>
```

## Executing the Program
```bash
leo execute <function_name> <input_1> <input_2> ...
```

## Playing the Game

### 1. Create a new game board
```bash
leo run new
```
|   |   |   |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 0 | 0 |
| 0 | 0 | 0 |

### 2. Player 1 makes a move
```bash
leo run make_move 1u8 1u8 1u8 "{ r1: { c1: 0u8, c2: 0u8, c3: 0u8 }, r2: { c1: 0u8, c2: 0u8, c3: 0u8 }, r3: { c1: 0u8, c2: 0u8, c3: 0u8 } }"
```
|   |   |   |
|---|---|---|
| 1 | 0 | 0 |
| 0 | 0 | 0 |
| 0 | 0 | 0 |

### 3. Player 2 makes a move
```bash
leo run make_move 2u8 2u8 2u8 "{ r1: { c1: 1u8, c2: 0u8, c3: 0u8 }, r2: { c1: 0u8, c2: 0u8, c3: 0u8 }, r3: { c1: 0u8, c2: 0u8, c3: 0u8 } }"
```
|   |   |   |
|---|---|---|
| 1 | 0 | 0 |
| 0 | 2 | 0 |
| 0 | 0 | 0 |
=======
<p align="center">
    <img width="1412" src="https://cdn.aleo.org/leo/banner.png">
</p>

<h1 align="center">The Leo Programming Language</h1>

<p align="center">
    <a href="https://circleci.com/gh/AleoHQ/leo"><img src="https://circleci.com/gh/AleoHQ/leo.svg?style=svg&circle-token=00960191919c40be0774e00ce8f7fa1fcaa20c00"></a>
    <a href="https://codecov.io/gh/AleoHQ/leo"><img src="https://codecov.io/gh/AleoHQ/leo/branch/testnet3/graph/badge.svg?token=S6MWO60SYL"/></a>
    <a href="https://discord.gg/5v2ynrw2ds"><img src="https://img.shields.io/discord/700454073459015690?logo=discord"/></a>
    <a href="https://github.com/AleoHQ/leo/blob/testnet3/CONTRIBUTORS.md"><img src="https://img.shields.io/badge/contributors-393-ee8449"/></a>
</p>
<div id="top"></div>
Leo is a functional, statically-typed programming language built for writing private applications.

## <a name='TableofContents'></a>Table of Contents

* [рџЌЋ Overview](#-overview)
* [вљ™пёЏпёЏ Build Guide](#-build-guide)
    * [рџ¦Ђ Install Rust](#-install-rust)
    * [рџђ™ Build from Source Code](#-build-from-source-code)
* [рџљЂ Quick Start](#-quick-start)
* [рџ§° Troubleshooting](#-troubleshooting)
* [рџ“– Documentation](#-documentation)
* [рџ¤ќ Contributing](#-contributing)
* [вќ¤пёЏ Contributors](#-contributors)
* [рџ›ЎпёЏ License](#-license)


## рџЌЋ Overview

Welcome to the Leo programming language.

Leo provides a high-level language that abstracts low-level cryptographic concepts and makes it easy to 
integrate private applications into your stack. Leo compiles to circuits making zero-knowledge proofs practical.

The syntax of Leo is influenced by traditional programming languages like JavaScript, Scala, and Rust, with a strong emphasis on readability and ease-of-use.
Leo offers developers with tools to sanity check circuits including unit tests, integration tests, and console functions.

Leo is one part of a greater ecosystem for building private applications on [Aleo](https://aleo.org/). 
The language is currently in an alpha stage and is subject to breaking changes.

## вљ™пёЏпёЏ Build Guide 

### рџ¦Ђ Install Rust

We recommend installing Rust using [rustup](https://www.rustup.rs/). You can install `rustup` as follows:

- macOS or Linux:
  ```bash
  curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
  ```

- Windows (64-bit):  
  
  Download the [Windows 64-bit executable](https://win.rustup.rs/x86_64) and follow the on-screen instructions.

- Windows (32-bit):  
  
  Download the [Windows 32-bit executable](https://win.rustup.rs/i686) and follow the on-screen instructions.

### рџђ™ Build from Source Code

We recommend installing Leo by building from the source code as follows:

```bash
# Download the source code
git clone https://github.com/AleoHQ/leo
cd leo

# Install 'leo'
$ cargo install --path .
```

Now to use leo, in your terminal, run:
```bash
leo
```

## рџљЂ Quick Start

Use the Leo CLI to create a new project

```bash
# create a new `hello-world` Leo project
leo new helloworld
cd helloworld

# build & setup & prove & verify
leo run
```

The `leo new` command creates a new Leo project with a given name.

The `leo run` command will compile the program into Aleo instructions and run it.

Congratulations! You've just run your first Leo program.

## рџ§° Troubleshooting
If you are having trouble installing and using Leo, please check out our [guide](docs/troubleshooting.md).

If the issue still persists, please [open an issue](https://github.com/AleoHQ/leo/issues/new/choose).

## рџ“– Documentation

* [Hello World - Next Steps](https://developer.aleo.org/leo/hello)
* [Leo Language Documentation](https://developer.aleo.org/leo/language)
* [Leo ABNF Grammar](https://github.com/AleoHQ/grammars/blob/master/leo.abnf)
* [Homepage](https://developer.aleo.org/overview/)

## рџ¤ќ Contributing
 
Please see our guidelines in the [developer documentation](./CONTRIBUTING.md)


## вќ¤пёЏ Contributors

View all Leo contributors [here](./CONTRIBUTORS.md).

## рџ›ЎпёЏ License
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](./LICENSE.md)

<p align="right"><a href="#top">рџ”ј Back to top</a></p>
>>>>>>> 74a0cb01619c7ed5bba5cd7fe7ed09ebeebafd7a
