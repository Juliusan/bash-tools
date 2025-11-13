# bash-tools

Bash scripts, which are needed in many cases

# Pdf

## `pdf.booklet`

The script prepares pdf file to be printed as a booklet.

```
pdf.booklet <input pdf>
```

An extension of the file provided in the parameter must be `pdf`. The result
is a pdf file in the same folder as the input file but with "Book" added to a
file name just before the extension. E.g. `pdf.booklet in.pdf` results in file
`inBook.pdf`. The file must be printed with short edge duplexing to obtain
correct booklet.

Packages `ghostscript`, `poppler-utils` and `psutils` are needed for this
script to work.

## `pdf.rotate`

The script rotates each page of pdf file counter clockwise:

```
pdf.rotate <input pdf>
```

The result is a pdf file in the same folder as the input file but with "R"
added to a file name just before the extension. E.g. `pdf.rotate in.pdf`
results in file `inR.pdf`.
The script can be used to correct orientation after printing to file several
slides in one page.
Package `pdftk` is needed for this script to work.

## `pdf.makesmaller`

The script shrinks the size of PDF file.

```
  pdf.makesmaller <input file> <output file>
```

# Latex

## `latex.compile`

Script to compile latex (.tex) file to pdf.

```
latex.compile <file>
```

# Golang

## `go.runSingleTestManyTimes`

A script runs a single Golang test `n` times (`n` is a first parameter). The
test is in folder, which is provided as a second parameter and is named as
provided in the third parameter. E.g.:

```
go.runSingleTestManyTimes 100 packages/name/tests TestSomething
```

The whole result is put into testFull.log file (each run is separated by
dedicated lines), each failed run result is put into testError*.log files.

If the first parameter is `clean`, the working directory is cleaned of files,
created by this script, and the script terminates.
