*This project has been created as part of the 42 curriculum by rmanzana*

# 42 Common Core

## Description

This repository is the entry point to my **42 Common Core** journey at [42 Barcelona](https://www.42barcelona.com/). The Common Core is the main part of the 42 curriculum: a sequence of projects, organised in **circles** (ranks), that goes from re-implementing the C standard library to building a full-stack web application, all learnt through peer-to-peer learning with no teachers and no lectures.

Every project lives in **its own repository**, with its own README explaining what it does, how it works and how to run it. This repository links them all together, and also holds the tools I used along the way: my editor and terminal configuration, a C++ project template, and my exam practice.

## Projects

### Circle 0

| Project | Language | Description |
|---|---|---|
| [libft](https://github.com/petandk/libft) | C | My own C library: re-implementations of `libc` functions, string utilities and linked lists, reused in later projects. |

### Circle 1

| Project | Language | Description |
|---|---|---|
| [born2beroot](https://github.com/petandk/born2beroot) | Shell / Sysadmin | A secure Debian server in a virtual machine: encrypted LVM, SSH, UFW, password policy, strict `sudo` and a monitoring script. |
| [get_next_line](https://github.com/petandk/get_next_line) | C | Reading a file descriptor one line at a time, with static variables and any buffer size. |
| [ft_printf](https://github.com/petandk/ft_printf) | C | A re-implementation of `printf()` with variadic functions. |

### Circle 2

| Project | Language | Description |
|---|---|---|
| [fract-ol](https://github.com/petandk/fract-ol) | C / MiniLibX | An interactive explorer of the Mandelbrot and Julia fractals, with zoom and navigation. |
| [pipex](https://github.com/petandk/pipex) | C | Reproducing the shell pipe `< infile cmd1 \| cmd2 > outfile` with `fork`, `pipe`, `dup2` and `execve`. |
| [push_swap](https://github.com/petandk/push_swap) | C | Sorting numbers with two stacks and as few operations as possible, using a cost-based greedy algorithm. |

### Circle 3

| Project | Language | Description |
|---|---|---|
| [minishell](https://github.com/petandk/minishell) | C | A bash-like shell with pipes, redirections, heredocs, environment variables, signals and built-ins. *(with gpolo)* |
| [philosophers](https://github.com/petandk/philosophers) | C | The dining philosophers problem, solved with threads and mutexes without deadlocks or data races. |

### Circle 4

| Project | Language | Description |
|---|---|---|
| [cub3d](https://github.com/petandk/cub3d) | C / MiniLibX | A Wolfenstein 3D-style raycaster with textured walls, minimap, collisions and mouse control. *(with pamanzan)* |
| [cpp00-namespaces-classes](https://github.com/petandk/cpp00-namespaces-classes) | C++ | Classes, member functions, streams, `static` and `const`. |
| [cpp01-memory-references](https://github.com/petandk/cpp01-memory-references) | C++ | Memory allocation, references and pointers to member functions. |
| [cpp02-operator-overloading](https://github.com/petandk/cpp02-operator-overloading) | C++ | Operator overloading and the Orthodox Canonical Form, with a fixed-point number class. |
| [cpp03-inheritance](https://github.com/petandk/cpp03-inheritance) | C++ | Inheritance, and the diamond problem solved with virtual inheritance. |
| [cpp04-polymorphism-abstract-classes](https://github.com/petandk/cpp04-polymorphism-abstract-classes) | C++ | Virtual functions, deep copies, abstract classes and interfaces. |

### Circle 5

| Project | Language | Description |
|---|---|---|
| [inception](https://github.com/petandk/inception) | Docker | A WordPress + MariaDB + NGINX infrastructure, each service in its own container built from scratch with Docker Compose. |
| [webserv](https://github.com/petandk/webserv) | C++ | An HTTP/1.1 server with an Nginx-inspired configuration file, static files, uploads and CGI. *(with pmorello and jaacosta)* |
| [cpp05-exceptions](https://github.com/petandk/cpp05-exceptions) | C++ | Exceptions and custom exception classes, through a simulated bureaucracy. |
| [cpp06-casts](https://github.com/petandk/cpp06-casts) | C++ | The four C++ casts: scalar conversion, serialization and runtime type identification. |
| [cpp07-templates](https://github.com/petandk/cpp07-templates) | C++ | Function templates and a generic `Array<T>` class template. |
| [cpp08-containers-iterators](https://github.com/petandk/cpp08-containers-iterators) | C++ | STL containers, iterators and algorithms, and an iterable `std::stack`. |
| [cpp09-btc-rpn-pmergeme](https://github.com/petandk/cpp09-btc-rpn-pmergeme) | C++ | A bitcoin price calculator, an RPN evaluator, and the Ford-Johnson merge-insertion sort. |

### Circle 6

| Project | Language | Description |
|---|---|---|
| [ft_transcendence](https://github.com/petandk/ft_transcendence) | TypeScript | A real-time multiplayer Pong platform with tournaments, chat, OAuth, stats and i18n, built with Next.js, NestJS, PostgreSQL and Docker. *(with akreise, dcampas, ebalana and pshcherb)* |

## Tools in this repository

### `dotfiles/`

The configuration I used on the campus computers.

| File | Description |
|---|---|
| `vimrc` | Vim setup with line numbers, 4-space indentation, search highlighting, folding, and plugins managed by [vim-plug](https://github.com/junegunn/vim-plug): NERDTree, EasyMotion, auto-pairs, buftabline, airline and vim-commentary. `Space` is the leader key, and `<Leader>p` inserts the 42 header. |
| `zshrc` | The 42 `USER` / `MAIL` variables for the header, and small helpers: `mkcd` (create and enter a directory) and `vagoc` (compile with the 42 flags). |
| `wezterm.lua` | A [WezTerm](https://wezfurlong.org/wezterm/) terminal configuration with a custom colour theme, fonts with ligatures, transparency, styled tabs, and keyboard shortcuts for tabs and panes with Vim-style navigation. |

To use them:

```bash
cp dotfiles/vimrc ~/.vimrc
cp dotfiles/zshrc ~/.zshrc
cp dotfiles/wezterm.lua ~/.wezterm.lua
```

### `cpp_template/`

The starting point for every C++ module exercise: a `src/` folder with a `main.cpp`, and a `Makefile` already set up with the module rules (`c++ -Wall -Wextra -Werror -std=c++98 -Wshadow`), automatic header dependencies (`-MMD`), object files in `obj/`, headers in `inc/`, and an extra `run` rule that builds and runs the program.

```bash
cp -r cpp_template ex00
# set NAME and SOURCE_FILES in the Makefile, then:
make run
```

### `exams/`

My practice for the Common Core exams.

| Folder | Content |
|---|---|
| `rank 05/` | C++ and C exercises: `bigint` (arbitrary-precision integers), `polyset` (set implementations on top of array and tree bags), `vect2` (a 2D vector class), `bsq` (biggest square in a map) and `life` (Conway's Game of Life). |
| `rank 06/` | `mini_serv`, a TCP chat server multiplexed with `select()`. It includes the successive versions of my solution, from the original to the final one that passed the exam, a tester, and step-by-step study notes (in Spanish). |

## Instructions

Each project is in its own repository. To get one:

```bash
git clone https://github.com/petandk/<project>.git
cd <project>
make
```

The README of each project explains its requirements, how to compile it and how to use it. Most projects are written for Linux, the operating system of the 42 computers.

## Resources

- [42 Network](https://www.42network.org/) and [42 Barcelona](https://www.42barcelona.com/)
- [The Norm — 42 coding standard](https://github.com/42School/norminette)
- Each project's README lists the resources specific to its topic.
