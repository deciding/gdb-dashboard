# GDB dashboard

GDB dashboard is a standalone `.gdbinit` file written using the [Python API][] that enables a modular interface showing relevant information about the program being debugged. Its main goal is to reduce the number of GDB commands needed to inspect the status of current program thus allowing the developer to primarily focus on the control flow.

![Screenshot](https://raw.githubusercontent.com/wiki/cyrus-and/gdb-dashboard/Screenshot.png)

[Python API]: https://sourceware.org/gdb/onlinedocs/gdb/Python-API.html

## Quickstart

Just place [`.gdbinit`][] in your home directory, for example with:

```
wget -P ~ https://git.io/.gdbinit
```

Optionally install [Pygments][] to enable syntax highlighting:

```
pip install pygments
```

Then debug as usual, the dashboard will appear automatically every time the inferior program stops.

Keep in mind that no GDB command has been redefined, instead all the features are available via the main `dashboard` command (see `help dashboard`).

Head to the [wiki][] to learn how to perform the most important tasks.

## DEBUG

repeat the command
```
$ rc [n] <cmd>
```

print to tty
```
> tty
$ da registers -output /dev/pts/7
```

step & break & print
```
$ stepi
$ break *0x000055555600ab80
$ p $rax
$ i r rax
```

record AS code
```
$ set logging file xxx
$ set logging on 
$ disas /m (/s)
$ set logging off
```

show code
```
$ x/50i $pc-8*18
```

[`.gdbinit`]: https://raw.githubusercontent.com/cyrus-and/gdb-dashboard/master/.gdbinit
[Pygments]: http://pygments.org/
[wiki]: https://github.com/cyrus-and/gdb-dashboard/wiki
