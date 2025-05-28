---
title: 'Rust isn\'t Hard'
date: 
permalink: /posts/2026/06/rust-isnt-hard/
tags:
  - blog
  - research
  - software-engineering
  - rust
---

So if you've been anywhere near the software development community in the last few years, you've probably heard a lot of people talking about Rust. It's been hailed as a language that makes it easier to write safe and efficient code, and it's been gaining popularity rapidly. Rust tools are popping out left and right, and the community is growing. However, Rust is frequently described as being difficult to learn with a steep learning curve. In particular, the borrow checker is often cited as a major hurdle for new users.

But is it really that hard?

No.

## The tooling ecosystem

So, one thing that makes Rust *so* compelling, is the surrounding tooling ecosystem. One of the critiques of C and C++ is that, the official commitees that govern the languages never adopted a standard set of tools. For starters, there are at least three major compilers for C and C++: GCC, Clang, and MSVC. Each of these compilers has its own set of extensions, options, tools, et cetera. While there are some commonly accepted practices (i.e. using MSVC for Windows development and GCC for Linux development), there is no single standard set of tools that everyone uses. This can lead to confusion and frustration, especially for new users. On top of this, each compiler has its own implementation of the standard library, which can lead to subtle differences in behavior between compilers, and availability of features. You need look no further than the implementation and adoption of C++20's modules to see how this can lead to fragmentation and confusion in the ecosystem.

Next, there is no single standard package manager for C and C++. While there are some popular package managers (e.g. vcpkg, Conan, Hunter), there is no single standard that everyone uses. On top of this, there is the not uncommon practice of installing packages via the system package manager (e.g. apt, yum, brew). This is a ***huge*** issue. It makes dependecies difficult to manage as you may have installed a dependency from a previous project that you forget to include on the Read Me making the environment difficult to reproduce. You may need a specific version of a dependency, but the system package manager only has the latest version. Or you may have a dependency that is not available in the system package manager at all. This can lead to confusion and frustration, especially for new users.

Related to the packagemanger, is the lack of a unified build system. In C and C++, the most widely used "build" system is CMake, and CMake is... well, not great. It is not particularlly intuitive, and can be difficult to debuge. It works, but I really don't want to have to learn yet another languge just to build my project. On top of this, IDE integration is often conflicting with virtual environment management. An example: I managed to cobble together a virtual environment manager using the `conda` ecosystem (initially through `miniconda`, later through `pixi`, and I really, really like `pixi`.) This created two problems with CMake and using Visual Studio Code as my IDE. 

First, CMake does not play well with virtual environments when installed as a system tool. I had to manually configure the CMake toolchain setting in VS Code to point to the correct environment. This worked, but it created a problem with the CMake extension for VS Code. The extension would not recognize the CMake executable in the virtual environment, and I had to manually configure the extension to use the correct path. Neither of these is a huge deal, but again, it adds complexity and increased the friction when it comes to reproducing the environment. The second option I tried was to install CMake in the virtual environment itself.

On top of this, CMake is not a build system, it is a build configuration system. It generates build files for other build systems (e.g. Make, Ninja, Visual Studio). This means that you need to learn how to use CMake, and then learn how to use the underlying build system. This can lead to confusion and frustration, especially for new users. Its just... annoying. I don't know of any C/C++ developer that actually likes CMake, and it seems most people just tolerate it because it is the de facto standard and there isn't anything better.

### But what about vcpkg?

So a brief asside about vcpkg. vcpkg is a package manager for C and C++ that is developed by Microsoft. It is designed to make it easier to manage dependencies in C and C++ projects, and it has been gaining popularity in recent years. Honestly, its great. It's exactly what I would want in a package manager for C and C++. It is easy to use, it has a large number of packages available, and it integrates well with Visual Studio and VS Code. On top of that, it is cross platform, so you can use it on Windows, Linux, and macOS which, when paired with the cross platform compatiblity of VS Code and CMake, and its tight integrations with both tools, makes it a great choice for C/C++ development.

However, it's package source is highly currated and is more limited than the `conda-forge` ecosystem. Specifically for me, it does not have a package for the Generic Mapping Tools (GMT), which is a package I use frequently for geospatial data analysis. You can somewhat get around this limited curation by enabling `vcpkg` to install directly from a source Git repo. This means that I will still have to manage dependencies manually, which is a pain. That said, if you absolutely must use C/C++, I would highly recommend using `vcpkg` as your package manager.

(Admittedly there are some other package managers and build systems out there, but I don't have experience with them, so I won't comment on them here. The `vcpkg` + `CMake` + VS/VS Code integration is about as good a set of tooling as I've seen for C/C++ development, and it is still not as good as the Rust tooling ecosystem.)

### Consider Python

Now, you might be thinking, why the hell does all of this matter? Well, take a look a Python.

Admittedly, Python's packaging ecosystem is a bit of a mess, but it has a single standard package manager (pip) that can manage a standard virtual environment, and has come to concensus around a single standard package description format (pyproject.toml). This make it much easier to get a new project up and running, and to reproduce environments. On top of that, the standardized environment description and package source means that - even with the fragmented ecosystem - you can usually recreate the same environment using different tools. That said - and I swear this isn't a Rust fanboy plug, the tool really is just that great - you should be using `uv` for any new Python project. If you need to manage non-Python dependencies, use `pixi` which is a drop-in replacement for `conda` that works with `uv` for Python management under the hood.

I can't help but think that part of the reason Python is so popular is because of its tooling ecosystem. Good tooling makes it easier to get started, and to reproduce environments. It lowers the barrier to entry, and makes it easier for new users to get up to speed. Pair that with an interpreted language that is easy to read and write, and you have a recipe for success.

### What is so good about Rust?

Rust, it seems, took the lessons learned from the mistakes made with the decades of C and C++ development, and the successes of Python, and built a language that is designed to be easy to use, with a great tooling ecosystem. Rust has a single standard compiler (rustc), a single standard package manager (Cargo) that doubles as the build system (Cargo), and a single standard linter (Clippy). These tools come packaged with the language and are installed via a single standard toolchain manager (rustup). Before you even go into the language design or Rust and the benefits it brings to the table, if it was *just* a tooling system for C and/or C++ development, it would still be a huge improvement over the current state of the art. No C/C++ compiler gives you notes and corrections on your code. No C/C++ package manager uses a simple `toml` file to describe your dependencies. No C/C++ build system is as easy to use as `cargo build`. No C/C++ linter is as comprehensive and easy to use as Clippy.

This makes it much easier to get started with Rust, and to reproduce environments. The tooling is designed to work together, and the community has adopted a set of best practices that make it easy to get started. The Rust community is also very welcoming and helpful, which makes it easier for new users to get up to speed. Plenty of other folks have talked about the borrow checker, memory safety, fearless asynchronous programming, and other language features that make Rust compelling, but I frankly don't care that much. Well, maybe about the borrow checker, as because of the way Rust works, if the program compiles, the only bugs you have left are logic bugs. This is a huge win for productivity in my book.

Additionally, and this is much more subjective, I find Rust's syntax to be much more readable and intuitive than C/C++. C++ can be... verbose. Overwhelmingly so at times. The common practice of throwing references and pointers around like confetti, and the use of templates, can make C++ code difficult to read and understand. Also, header files are dumb. It is 2025 when I'm writing this, and if you're working in the C++ ecosystem, you are still working with a compiler that reads and comprehends your code only line-by-line in a single pass. This isn't to say that Rust won't ever be verbose, lifetime annotations can be a bit much at times, but the borrow checker and compiler can frequenlty infer things about your code that you would have to explicitly annotate in C/C++. This makes Rust code more concise and easier to read.

As very simple example of this consider looping through a list of integers and printing out the sum. In C++, you might write something like this:

```cpp
#include <iostream>
#include <vector>
#include <numeric>

int main() {
    std::vector<int> numbers = {1, 2, 3, 4, 5};
    int sum = std::accumulate(numbers.begin(), numbers.end(), 0);
    std::cout << "Sum: " << sum << std::endl;
    return 0;
}
```

In Rust, you could write the same thing like this:

```rust
fn main() {
    let numbers = vec![1, 2, 3, 4, 5];
    let sum: i32 = numbers.iter().sum();
    println!("Sum: {}", sum);
}
```

Now, we can ignore the import statements and the `return 0;` and effectively compare the same three lines of code. The C++ version is much more verbose. Consider only the initial declaration of the `numbers` variable. In C++, you have to specify the type of the vector, the type of the elements in the vector, and the initial value. In Rust, you can use type inference to let the compiler figure out the type of the vector and its elements. This makes Rust code more concise and easier to read. You could also manually specify the type of the vector in Rust:

```rust
let numbers: Vec<i32> = vec![1, 2, 3, 4, 5];
```

And it does get a bit more verbose, but even still, I find this to be more readable than the C++ version. Next is the summation. `std::accumulate`? What, no I just want to sum up the numbers! Oh, wait, that's what `accumulate` does? Could've fooled me, and wait, you point it to the beginning and end of the vector? Why not just let me use the vector directly? In Rust: its the list (vector), I want to iterate through it (`.iter()`), and get the sum (`.sum()`). Makes perfect sense.

I think the output statement stands on its own without needing further explanation.

I also generally find Rust's grammar to be more intuitive than C/C++. C, C++, C#, and Java follow this convetion of `<type> <name> = <value>;` for variable declarations, and `<return type> <name>(<args>) { <body> }` for function declarations. I guess this makes sense? It is not too hard to follow but Rust's `let <name>: <type> = <value>;` and `fn <name>(<args>) -> <return type> { <body> }` feels much more natural to me. 

As an asside, Rust's similarity and syntax to Python seems to me to present a major advantage in the 'prototype in <interpreted language>, deploy in <compiled language>' workflow. Rust to me, really just feels like a more verbose version of Python.
