# Rustic Knight

Rustic Knight is a high-performance chess engine developed in Rust, leveraging advanced algorithms for an efficient and powerful chess-playing experience.

## Key Features

### Search

- **PV Search with Negamax**: Utilizes the Negamax framework to efficiently explore the game tree.
- **Aspiration Windows**: Dynamically narrows the search window based on previous evaluations.
- **Transposition Table**: Stores previously computed positions for efficient re-use.
- **Quiescence Search**: Extends search beyond quiet positions, considering volatile ones to avoid the horizon effect.

### Extensions and Reductions

- **Check Extension**: Extends the search for check moves due to their high significance.
- **LMR (Late Move Reduction)**: Reduces search depth for later moves in the move ordering.

### Pruning Techniques

- **Alpha-Beta Pruning**: Reduces the number of nodes evaluated.
- **Null Move Pruning (NMP)**: Simulates no move to allow aggressive pruning.
- **Reverse Futility Pruning (RFP)**: Prunes unlikely moves to improve the position.
- **SEE in Quiescence Search**: Uses Static Exchange Evaluation to prune unfavorable captures.

### Move Ordering

- **Hash Move**: Prioritizes the most promising move from previous searches.
- **SEE for Capturing Moves**: Evaluates and prioritizes captures.
- **History Heuristic and Killer Moves**: Orders moves based on historical effectiveness and previous pruning success.
- **Additional Criteria**: Bonuses for moves like castling.

### Static Evaluation

- **Texel Tuning**: Optimizes evaluation parameters using game outcomes.
- **Piece Weights and Square Tables**: Assigns values based on piece strength and positions.
- **Additional Factors**: Considers tempo, piece mobility, and specific bonuses/penalties like bishop pair, passed pawns, and rook positioning.

### Time Management

- **Dynamic Time Allocation**: Adjusts search time based on remaining time and increments.
- **Time Limit Abortion**: Aborts the search if time exceeds limits, returning the best move found.

# Quick compiling tips

The engine includes a Makefile, which makes building the engine easier. If you wish to build the engine yourself, you
can find some quick tips below. These are meant for people who have some
experience with setting up build environments, or have them installed
already.

## Build environment

- [Install Rust for your platform](https://www.rust-lang.org/tools/install)
- Windows: [Install MSYS2](https://www.msys2.org/)
  - Make sure you install the following parts:
    - CoreUtils
    - BinUtils
    - GCC
    - Make
- Make sure you install the correct Rust target for your platform, using
  Rustup:
  - Linux:
    - **stable-x86_64-unknown-linux-gnu**
  - Windows:
    - **stable-x86_64-pc-windows-gnu** (This toolchain creates compiles that
      are compatible with the GNU GDB-debugger.)
    - **stable-x86_64-pc-windows-msvc** (This toolchain creates compiles that
      are compatible with Windows/Visual Studio's debugger. This will
      require the Microsoft Visual C++ Build Tools, because it uses the
      Microsoft Linker.)
- Install Git for your platform.

## Building Rustic Knight

- Start the terminal for your platform: MSYS2 (MinGW64 or MinGW32
  version) for Windows, Terminal on Mac, and for Linux, your favorite
  terminal emulator.
- Clone Rustic: "git clone https://github.com/mvanthoor/RusticKnight.git"
- Switch to the "RusticKnight" folder.
- Run "make" (Windows, Linux).
- The Makefile will build Rustic Knight for the operating system and CPU you're running on.

```

```
