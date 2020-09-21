# What is this?

I love [Cognitect dev-tols](https://www.cognitect.com/dev-tools/), particularly [REBL](https://github.com/cognitect-labs/REBL-distro).

I use [CIDER](https://github.com/clojure-emacs/cider) in [Emacs](https://www.gnu.org/software/emacs/), but [nREPL](https://nrepl.org/nrepl/0.8/index.html) does not current play well with REBL.

This repo provides the information necessary to use REBL how I use it in CIDER.

# How do I use it?

## deps.edn

I may add [lein](https://leiningen.org) content in the future, but I don't use Leiningen.

Add the appropriate alias to your `deps.edn`.

## .dir-locals.el

Add .dir-locals.el to your project root, or add the contents of .dir-locals.el to your existing .dir-locals.el.

This ensures that your CIDER repl starts with the correct deps (i.e. the appropriate REBL alias).

## .emacs

Add the code in `.emacs` to _your_ `.emacs` or `init.el` or however you want to get it into emacs.

This provides the functions for sending forms to REBL.

# Workflow

Once the code/data is in the appropriate places, I `cider-jack-in` in my project. REBL will automatically open.

Send code to REBl with the appropriate function:

* rebl-eval-last-sexp (`C-x C-r`) - Send, and eval, the previous sexp to REBL.
* defun rebl-eval-defun-at-point (`C-S-x`) - Send, and eval, the current top-level form to REBL

# Other things

* [nREBL](https://github.com/RickMoynihan/nrebl.middleware) - Uses nREPL middleware to send _all_ forms to REBL.
* [nREPL REBL](https://github.com/DaveWM/nrepl-rebl) - Same idea, different author.

