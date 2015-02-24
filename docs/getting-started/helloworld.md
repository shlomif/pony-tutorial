Our first program will be a very traditional one. We're going to print "Hello, world!". First, create a directory called `helloworld`:

```
$ mkdir helloworld
$ cd helloworld
```

__Does the name of the directory matter?__ Yes, it does. It's the name of your program! When your program is compiled, the resulting executable binary will have the same name as the directory your program lives in.

# The code

Then, create a file in that directory called `main.pony`. 

__Does the name of the file matter?__ Not to the compiler, no. Pony doesn't care about filenames other than that they end in `.pony`. But it might matter to you! By giving files good names, it can be easier to find the code you're looking for later.

In your file, put the following code:

```
actor Main
  new create(env: Env) =>
    env.out.print("Hello, world!")
```

# Compiling the program

Now compile it:

```
$ ponyc
Building .
Building builtin
Generating
Optimising
Writing ./helloworld.o
Linking ./helloworld
```

Look at that! It built the current directory, `.`, plus the stuff that is built in to Pony, `builtin`, it generated some code, optimised it, created an object file (don't worry if you don't know what that is), and linked it into an executable with whatever libraries were needed. If you're a C/C++ programmer, that will all make sense to you, otherwise it probably won't, but that's ok, you can ignore it.

__Wait, it linked too?__ Yes. You won't need a build system (like `make`) for Pony. It handles that for you (including handling the order of dependencies when you link to C libraries, but we'll get to that later).

# Running the program

Now we can run the program:

```
$ ./helloworld
Hello, world!
```

Congratulations, you've written your first Pony program! Next, we'll explain what some of that code does.