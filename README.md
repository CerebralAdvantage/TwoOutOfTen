# TwoOutOfTen
generate two random numbers, fast

## The Goal
pick two numbers between 1 and ten-- I MEAN between 0 and 9!

### The Constraint(s)
1. They have to be different
2. They have to be between 0 and 9 inclusive
3. They have to be random (at least pseudo-random)
4. The process should be fast

### TL;DR
It's pretty easy to use rand() to create two single digit, random values.  But if they're the same, you need to do things a little differently.  For instance you need to pick the second number, over and over, until it is different from the first.  Usually this is one extra pick.  Plus, it should rarely happen.  But running the rand() system call over and over is not the fastest way to proceed.  You might notice this if you need to pick, say 10,000,000 times.  There are good solutions that rely on the pseudorandom rand() call for just a few hundred times.  This is one such algorithm.

#### Some Prep
Prior to running the program, we generate some values and store them. We can use these values over and over, but it helps to not have to regenerate the lists, every run.  They are two lists of digits, but they are different enough to require two.  So before we run our program for the first time, we generate these lists.  Once.  The program pregen.c generates and saves these values

#### Run this, once per program start...
