c-eldoc.el
==========

Display description of the function under the cursor.

Installation
============

First, download and compile `c-eldoc.el`

    wget http://github.com/nflath/c-eldoc/raw/master/c-eldoc.el

Then, place `c-eldoc.el` into your site-lisp directory.

Finally, add following lines to your emacs config file (e.g. `.emacs`).

    (add-hook 'c-mode-hook 'c-turn-on-eldoc-mode)
    (add-hook 'c++-mode-hook 'c-turn-on-eldoc-mode)

Customization
=============

Cache
-----

`c-eldoc.el` uses cache to reduce the times of compilation. This cache has expiration time (default 30 seconds) and you can customize this value.

    (setq c-eldoc-buffer-regenerate-time 60)

Compile options
---------------

You can customize the compiler and the compile options.

Here are the default values.

    (defvar c-eldoc-cpp-command "/lib/cpp ") ;; compiler
    (defvar c-eldoc-cpp-macro-arguments "-dD -w -P")
    (defvar c-eldoc-cpp-normal-arguments "-w -P")
    (defvar c-eldoc-includes "`pkg-config gtk+-2.0 --cflags` -I./ -I../ ") ;; include flags

To customize them, use `setq`.

    (setq c-eldoc-cpp-command "/usr/local/bin/clang")
