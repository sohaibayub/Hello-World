### Useful Commands
#### Emit LLVM IR

```
> clang -S -emit-llvm file.c -o file.bc
```

 produces `file.bc` with textual LLVM IR.

`-S` like in gcc says emit textual assembly rather than assembled binary

if `-o file.bc` is omitted, it will generate `file.ll`.

#### Compile LLVM IR to assembly
```
> llc file.bc
```

produces file.s with assembly (defaulting to machine architecture the command is run on). [LLC docs are available here.](http://llvm.org/cmds/llc.html)

#### Run LLVM bitcode direclty
```
lli file.bc
```

executes the program in `file.bc` (it can be textual or binary bitcode). [LLI docs are available here.](http://llvm.org/docs/CommandGuide/lli.html)

### ELLCC (Online experimentation)
All of the above can be done on local llvm installation as well. But it might help to experiment online at [ELLCC](http://ellcc.org/demo/index.cgi): http://ellcc.org/demo/index.cgi

### Pass
A pass needs a `Makefile` and a `.exports` file (don't know why it needs an `.exports` file.)

#### Build Pass
Run

```
> gmake
```

from inside the pass directory.

#### Test Pass
Run

```
> opt -S -load ../../../Debug+Asserts/lib/<pass_name>.so -<pass_command_line_argument> < <input_bc_file> > <output_bc_file>
```

`-S` is to ensure any output is generate as textural IR.

[More information is available in Writing a Hello World Pass.](http://llvm.org/docs/WritingAnLLVMPass.html)


### Issues:
* Difficulty finding header files (e.g. I had to spend a good 15 minutes on finding llvm/Intrinsic.h)
* Isn't there a getOrInsertGlobalVariable function?

### OCCAM INSTALL NOTES:
- export OCCAM_SRC=`pwd`/OCCAM is actually export OCCAM_SRC=`pwd`
- even if adding all the variables to .profile, 'export ' needs to precede the variable
- add export LD_LIBRARY_PATH=/usr/local/lib:${LD_LIBRARY_PATH}
