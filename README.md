# Backpropagation-TicTacToe: sequential vs OpenMP vs OpenCL

A university study that trains a small neural network to play Tic Tac Toe and compares three implementations of backpropagation: sequential C++, multi-core with OpenMP, and GPU with OpenCL.

*Fork of an upstream backpropagation example in C. Everything below was added on top of it by me and a classmate.*

## Context

A paper-style project from the Electrical and Electronics department at my university, co-written with a classmate. The README is the written report, in Spanish. It was uploaded in August 2019.

## What we added to the upstream code

- A Tic Tac Toe network: 9 inputs (the board), 40 hidden neurons and 1 output (the chosen move), trained before the game starts.
- Three builds of the same training loop: sequential, OpenMP (`#pragma omp` on the parallel sections) and OpenCL (host code that creates and queues a GPU kernel).
- A playable command-line interface for the sequential version.
- A written report: problem statement, implementation, the error-versus-epoch curve, and timing results. The report notes that at low iteration counts the parallel overhead outweighs the gain.

## Stack

C++, OpenMP, OpenCL, Visual Studio 2015 (MSVC), CMake for the OpenCL build.

## Run it

Open the `.sln` files in Visual Studio, or build the OpenCL folder with CMake and an OpenCL SDK.

## Looking back (2026)

I committed build output (`.exe`, `.pdb` and IDE caches) along with the source. Today I would keep only the source, use one CMake build for all three variants, and publish the benchmark as a reproducible script.
