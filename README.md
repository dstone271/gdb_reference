# gdb_reference
Reference information for use of the GDB tool

## Overview
The GDB (GNU Debugger) tool is very useful for debugging and analyzing running code. Below are some helpful commands. For setup, GDB was already installed on my linux computer, probably through GCC development packages I had installed previously. To debug a program, you must compile it with the "-g" flag, so that debugging symbols are included. You can use breakpoints on line numbers and functions and watchpoints on variables to pause the execution of the code during a debugging session. An important concept is the call stack, which holds the context of a funtion call in a stack frame at each level of the stack. There are many advanced things you can do with GDB, including looking at memory and assembly code.


## Commands
Compile with debugging symbols
> g++ -g program.cc -o app

Run program with gdb debugger
> gdb app
(gdb) run arg1 "arg2" ...
(gdb) kill

Exit debugger
(gdb) quit

Get help
(gdb) help
(gdb) help <cmd>

List current spot in program
(gdb) list

Progress through code
Go line by line, but not into function calls
(gdb) next
Go line by line and into function calls
(gdb) step
Continue from a break or stopped location
(gdb) continue
Continue until the end of the current function and its return
(gdb) finish

Work with variables
Examine a variables value
(gdb) print x
Set value of a variable
(gdb) set x = 3

Call functions linked within program
(gdb) call func()

Working with the call stack
List out the stack frames of the call stack
(gdb) backtrace
Change stack frames
(gdb) frame #
Display info on current stack frame
(gdb) info frame
Display list of variables in the current stack frame
(gdb) info locals
Display list of argumnets of the current stack frame
(gdb) info args

Working with breakpoints
Set a breakpoint on a line of a file (or the main file)
(gdb) break [file:]#
Set a breakpoint on a function name
(gdb) break func
(gdb) break TestClass:Func(int)
Set a temporary breakpoint
(gdb) tbreak
Get a list of breakpoints
(gdb) info breakpoints
Disable breakpoints
(gdb) disable #
Skip a breakpoint
(gdb) ignore break# time#

Working with watchpoints
watchpoints are listed along with breakpoints
Set a write watchpoint
(gdb) watch x
Set a read watchpoint
(gdb) rwatch x
Set a read & write watchpoint
(gdb) awatch x
Disable a watchpoint
(gdb) disable #

Advanced Things
Examine what is stored in memory
(gdb) x/[count][format][size] mem_address
See what's in processor registers
(gdb) info registers
Debug with a core file
(gdb) core core_file
Step through code at the instruction level
(gdb) nexti
(gdb) stepi
See the assembly code
arguement is a memory address. This could be a name of a function
(gdb) disassemble mem_address


## Resources
Official website:
https://sourceware.org/gdb/

RMS's gdb Tutorial
http://www.unknownroad.com/rtfm/gdbtut/gdbtoc.html
