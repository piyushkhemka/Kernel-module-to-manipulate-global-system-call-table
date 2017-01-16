Linux prohibits a loadable module from changing the global system call vector/table.
Linux makes it hard to change system calls, either globally or on a per process (or process group) basis.
Having different syscalls per process is useful for various scenarios. For example, to add tracing/printf
messages for certain syscalls; to override the default behavior of a system call
(e.g., to encrypt/decrypt file names); to prevent certain
processes from invoking syscalls they shouldn't (e.g., a Web server typically has no business
invoking mkdir(2), unless it was hijacked).

We propose a solution for a more fine grained
control over per process system call execution. Using IOCTL, api calls and modified version of
clone, we allow addition, removal, assignment of new system call during runtime and blocking system calls.


*** Code available on request.
