## Debugging 
> is the process of finding and resolving defects or problems within a computer program that prevent correct operation of computer software or a system

###strategies for Debugging
- Incremental and bottom-up program development.
>Bottom-up development maximizes the benefits of incremental development. With bottom-up development, once a piece of code has been successfully tested, its behavior won't change when more code is incrementally added later. Existing code doesn't rely on the new parts being added, so if an error occurs, it must be in the newly added code (unless the old parts weren't tested well enough).

-  Instrument program to log information. 
> Print statements are inserted. Although the printed information is effective in some cases, it can also become difficult to inspect when the volume of logged information becomes huge. In those cases, automated scripts may be needed to sift through the data and report the relevant parts in a more compact format. 

- Instrument program with assertions
> Assertions check if the program indeed maintains the properties or invariants that your code relies on. 

- Use debuggers.
> Setting breakpoints in the program, stepping into and over functions, watching program expressions, and inspecting the memory contents at selected points during the execution will give all  the needed run-time information without generating large, hard-to-read log files.

- Backtracking
>One option is to start from the point where to problem occurred and go back through the code to see how that might have happened.

- Problem simplification.
> The approach is to gradually eliminate portions of the code that are not relevant to the bug. 

- Bug clustering.
> If a large number of errors are being reported, it is useful to group them into classes of related bugs (or similar bugs), and examine only one bug from each class. The intuition is that bugs from each class have the same cause (or a similar cause). Therefore, fixing a bug with automatically fix all the other bugs from the same class (or will make it obvious how to fix them).

- Error-detection tools.
> Such tools can help programmers quickly identify violations of certain classes of errors. e.g 
`Purify` dynamic tool that instruments programs to identify memory errors, such as invalid accesses or memory leaks. 