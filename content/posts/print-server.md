---
title: "Print Server"
date: 2021-11-17T18:46:19-05:00
draft: false
---

### What is this thing?

In linux, all of the printing is done with something called a print server. [CUPS][1] is the server that I installed on this machine. Normally you would have an actual printer connected to the computer, but since this is a computer in the cloud we don't really have that option. So I though it would be cool if it did the next best thing.

### Print to PDF

First you need to install the CUPS server and PDF drivers. 

```sh
sudo apt install cups
sudo apt install cups-pdf
sudo apt install printer-driver-cups-pdf
```

Once that is complete you can start printing whatever you would like to PDF documents with the `lp` command.

Need to print the contents of a log file to a PDF, `cat file.log | lp` and in your ~/PDF folder a new PDF will be created. Want the manual page for lp in a PDF? No problem! `man lp | lp` 

There is a lot of other printer commands you can check out after doing this install. Check out https://www.cups.org/doc/options.html for more info.

[1]: https://en.wikipedia.org/wiki/CUPS