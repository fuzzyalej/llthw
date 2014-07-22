<ol class="breadcrumb">
  <li><a href="/">Home</a></li>
  <li><a href="/book/">Book</a></li>
  <li><a href="/book/1-0-0-overview/">Part One: Grokking Lisp</a></li>
  <li><a href="/book/1-02-00-input-output/">Printing, Strings, and Streams</a></li>
  <li class="active">Exercise 14: Pathnames</li>
</ol>

# Exercise 14: Pathnames

Lisp has a special way of handling files from your computer: *pathname* objects. They allow Lisp to handle file-names, for the most part, in a platform-agnostic manner.  If they seem like overkill, just keep in mind how many different platforms and file-systems Lisp supports.

Pathname objects are represented using the reader macro syntax `#P"..."`; they look like strings preceded by a Sharpsign-P, but they have a lot of internal structure you have to know about.  Let's take a look at what you can get out of a seemingly simple pathname:

```lisp
(truename ".")
(pathname-directory (truename "."))
(pathname-host (truename "."))
(pathname-name (truename "."))
(pathname-type (truename "."))
```

You'll get `nil` back for `pathname-name` and `pathname-type`.  But now let's create a new file with your text editor named "llthw-ex-1-2-14.lisp" and save it in the folder on your computer you got back from `(truename ".")`. If you changed the default folder to open SBCL in, like you were instructed to, this should be your home folder, or a folder dedicated to your Lisp code.

In "llthw-ex-1-2-14.lisp" enter the following code and save it again:

```lisp
;; an empty Common Lisp file
```

Back at the REPL, try this now:

```lisp
(truename "llthw-ex-1-2-14.lisp")
(pathname-name (truename "llthw-ex-1-2-14.lisp"))
(pathname-type (truename "llthw-ex-1-2-14.lisp"))
```

<ul class="pager">
  <li class="previous"><a href="/book/1-02-13-more-format/">&laquo; Previous</a></li>
  <li><a href="/book/">Table of Contents</a></li>
  <li class="next"><a href="/book/1-03-0-getting-input-from-users/">Next &raquo;</a><li>
</ul>