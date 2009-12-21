![Smex](http://sites.google.com/site/cumulatm/home/smex-logo.png)

## Smex

Smex is a M-x enhancement for Emacs. Built on top of Ido, it provides
a convenient interface to your recently and most frequently used
commands. And to all the other commands, too.

## Get started

* Download Smex.

* Add Smex to your load path. [(Find out more.)](http://www.emacswiki.org/emacs/InstallingPackages)

* To auto-start Smex every time you open Emacs add these lines to your .emacs file:
        (require 'smex)
   Put this line at the very end of your .emacs file:
   (It should be run after all your other Emacs packages have been loaded.)
        (smex-initialize)
   [Starter Kit](http://github.com/technomancy/emacs-starter-kit/) users should add the following instead:
        (eval-after-load "init.el" '(smex-initialize))
   Bind some keys:
        (global-set-key (kbd "M-x") 'smex)
        (global-set-key (kbd "M-X") 'smex-major-mode-commands)
        (global-set-key (kbd "C-c M-x") 'smex-update-and-run)
        ;; This is your old M-x.
        (global-set-key (kbd "C-c C-c M-x") 'execute-extended-command)

* Run Smex. (Type M-x, if that's your key binding).

The commands are displayed in an Ido completion buffer, ordered by
relevance.  The 7 most recently executed commands come first, the rest
are sorted by frequency of use, command length and in alphabetical
order.

Ido completion in 10 seconds: Typing selects matching commands:
e.g. 'lnmd' matches 'line-number-mode'. `C-s`/`C-r` switches to the
next/previous match. Enter executes the selected command.
   
## Learn more

### Show only major mode commands
`smex-major-mode-commands` runs Smex, limited only to commands that
are relevant to the active major mode. Try it with Dired or Magit.

### Command help
`C-h f`, while Smex is active, runs `describe-function` on the
currently selected command.

`M-.` jumps to the definition of the selected command.

### Show unbound commands
`smex-show-unbound-commands` shows frequently used commands that have
no key bindings.

### Persistence
Smex keeps a file to save its state betweens Emacs sessions. The
default path is '~/smex.save'; you can change it by setting the
variable `smex-save-file`.

### Cache maintenance
To guarantee snappiness, Smex maintains command caches - which,
unfortunately, can not be automatically refreshed when new commands
are defined (or unloaded).

Run `smex-update-and-run` to update and invoke Smex, e.g. to access
commands of a library you have just loaded.

Additionally, you can teach Smex to update its caches after Emacs has
been idle for 60 seconds: `(smex-auto-update)`. (Provide an integer
argument for a custom time period in seconds.)

### History
Set `smex-history-length` to change the number of recent commands that
Smex keeps track of.

### Prompt
Set `smex-prompt-string` for a custom prompt.

## Appendix

Smex is my first venture into Elisp. I'd be glad to receive patches,
comments and your considered criticism.

*Have fun with Smex!*
