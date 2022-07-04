#org-xournal

Minor mode for working with [[https://xournal.github.io/][xournal]] notes, sketches etc. in org mode.

Based on [org-xournal](https://gitlab.com/vherrmann/org-xournal/-/tree/master) by Valentin Herrmann.

If you are using Doom emacs you can add this to your =packages.el=:
#+begin_src emacs-lisp
(package! org-xournal
  :recipe (:host github
           :repo "luis-marques/org-xournal"
           :files ("resources" "*.el")))
#+end_src

and this to your =config.el=:
#+begin_src emacs-lisp
(use-package! org-xournal
  :config
  (add-hook 'org-mode-hook 'org-xournal-mode))
#+end_src

=org-xournal= creates a new org link type called =xournal= that:
- when clicked on, opens xournal for editing the file linked, and
- shows the updated image preview inline if =org-xournal-mode= is enabled.

To use the package, you need to enable the minor mode =org-xournal-mode= in org buffer with =xournal= links like this =[[xournal:./some-file.xopp][image]]=. To create new files within the buffer itself, try calling =org-xournal-insert-new-image=.

To change the default template, hack =#'org-xournal-template-getter=. For example, you can use your favorite selection/completion like =ivy= or =helm=.
