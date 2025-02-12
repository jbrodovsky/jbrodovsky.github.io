---
title: 'Rust and C++ for Advent of Code'
date: 2024-12-01
permalink: /posts/2024/12/advent-of-code/
tags:
  - blog
  - advent-of-code-2024
---

So 2024 is wrapping up with some changes for me. I'm staring a new position at Temple University with the [Boni Lab](mol.ax) as a Research Associate where I'll be working on designing software that simulates malaria out breaks and models drug resistance. A little outside my wheelhouse as a robotics student to say, but the lab's staff have more of a computer science and mathematics background despite being housed in the biology department. 

It's been a while since I've worked in C++, so I figured I'd dive in to [Advent of Code](https://adventofcode.com/) for the first time and complete the puzzles in C++. That said, I've also been taking an interest in Rust. Partially due to the US government taking a policy on memory safe languages, but also due to its apparent ergonomics. Frankly, with some of my research, what I've really found myself wanting is a more strongly typed version of Python, that gets the speed of native machine code. Numba gets a lot of the way there, but largely requires that you frame and work your calculations within a vectorized NumPy-based ecosystem. Useful, but I've found in my particle filter work, that that when you're trying to do calculations on an N x 15+ matrix, it isn't uncommon to forget if your velocity quantities start on index 3, 6, or something else. Being able to use a simple struct object where I can just do `particle.pos_x += particle.vel_x * dt + noise` is a much more ergonomic approach, but to do so I'd need to go down to a compiled language.

I've always had a love-hate relationship with C++, even worse with C. I still don't really get header files and maybe it's my Python and even worse Matlab experience, I'm much more accustomed to `self.my_data` syntax than the scoping in C++. Its not neccessarily better or worse, just different. That said, when I simply *look* at Rust, it looks like what I want. The syntax looks like Python and C/C++ had a baby. The borrow checker allows for compiled performance with Python memory safety (and I know that probably made some Rustaceans cringe) by keeping the guard rails on to make sure I don't end up accidentally blowing my leg off.

So I plan on doing the 2024 Advent of Code twice: first time around in C++ to knock off some - sorry, pun incoming - rust, and second time around using Rust to star to learn the language and the syntax. I'll be posting my solutions and comparisons along the way and my thoughts on working in both.