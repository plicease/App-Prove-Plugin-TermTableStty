# App::Prove::Plugin::TermTableStty ![linux](https://github.com/uperl/App-Prove-Plugin-TermTableStty/workflows/linux/badge.svg) ![macos](https://github.com/uperl/App-Prove-Plugin-TermTableStty/workflows/macos/badge.svg)

Set the size of the console for Term::Table using stty size

# SYNOPSIS

From command-line:

```
prove -PTermTable
```

From .proverc:

```
-PTermTable
```

# DESCRIPTION

Some of the [Test2::Tools](https://metacpan.org/pod/Test2::Tools) provide some pretty tables for comparing deltas from failed tests.  It tries to 
detect the size of the terminal so that long lines can be wrapped and the tables remain readable.  Unfortunately
when you run the tests under `prove`, `stdout` is redirected to a non-terminal and the size of the terminal
cannot be detected.  This plugin will detect the size of the terminal using `/dev/tty` instead of `stdout` and
set the appropriate environment variable so that tables can be printed to use the entire terminal diameter.

I understand why 80 columns is the default for when you do not know the size of a terminal, but really who here 
in 2018 is actually using an 80 column display?  sigh.

This module is similar to [App::Prove::Plugin::TermTableStty](https://metacpan.org/pod/App::Prove::Plugin::TermTableStty) but has fewer prereqs and requires a platform that
supports the `stty size` command.

# SEE ALSO

- [Test2](https://metacpan.org/pod/Test2)
- [App::Prove](https://metacpan.org/pod/App::Prove)

# AUTHOR

Graham Ollis <plicease@cpan.org>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2018 by Graham Ollis.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
