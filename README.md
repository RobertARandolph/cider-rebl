# What is this?

I love [Cognitect dev-tools](https://www.cognitect.com/dev-tools/), particularly [REBL](https://github.com/cognitect-labs/REBL-distro).

I use [CIDER](https://github.com/clojure-emacs/cider) in [Emacs](https://www.gnu.org/software/emacs/), but [nREPL](https://nrepl.org/nrepl/0.8/index.html) does not current play well with REBL. There are [other solutions](#other-things), but they don't work how I want them to.

This repo provides the information necessary to use REBL how I use it in CIDER.

# How do I use it?

The default behaviour for REBL with non-nREPL clients and with ([nREPL middleware's](#other-things)) is to send all forms to REBL or use REBL as a REPL.

I prefer to only send specific forms to REBL as I work. This allows me to easily find the dozen or so things that I care about inspecting in a REPL session that might have 100(0)s of evaluations.

# Installation

## deps.edn

I may add [lein](https://leiningen.org) content in the future, but I don't use Leiningen.

Depending on if you use jdk8 or jdk11+, add the appropriate alias from [deps.edn](https://github.com/admiralbumblebee/cider-rebl/blob/master/deps.edn) to your `deps.edn`.

The important difference from the Cognitect prescribed deps is the `:main-opts`. If you already use REBL then you can just change that.

## .dir-locals.el

Add [.dir-locals.el](https://github.com/admiralbumblebee/cider-rebl/blob/master/.dir-locals.el) to your project root, or add the contents of [.dir-locals.el](https://github.com/admiralbumblebee/cider-rebl/blob/master/.dir-locals.el) to your existing .dir-locals.el.

This ensures that your CIDER repl starts with the correct deps (i.e. the appropriate REBL alias).

## .emacs

Add the code in [.emacs](https://github.com/admiralbumblebee/cider-rebl/blob/master/.emacs) to _your_ `.emacs` or `init.el` or however you want to get it into emacs.

This provides the functions for sending forms to REBL.

# Workflow

Once the code/data is in the appropriate places, I `cider-jack-in` in my project. REBL will automatically open.

Send code to REBl with the appropriate function:

* rebl-eval-last-sexp (`C-x C-r`) - Send, and eval, the previous sexp to REBL.
* defun rebl-eval-defun-at-point (`C-S-x`) - Send, and eval, the current top-level form to REBL

REBL's taps are active and will capture anything `tap>`'d.

# Other things

* [nREBL](https://github.com/RickMoynihan/nrebl.middleware) - Uses nREPL middleware to send _all_ forms to REBL.
* [nREPL REBL](https://github.com/DaveWM/nrepl-rebl) - Same idea, different author.

