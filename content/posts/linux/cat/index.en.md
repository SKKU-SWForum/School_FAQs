---
title: "Linux command: cat"
date: 2021-04-29T00:07:30+09:00
draft: false
hero: images/cat-hero.png
menu:
  sidebar:
    name: cat
    identifier: linux-cat
    parent: linux
    weight: 10
---


# cat 
concatenate files and print on the standard output

{{< vs 2 >}}

---
## Usage
Used to verify the contents of a file.

{{< vs 2 >}}

---
## Options

   | Useful options | Usage                                                                              |
   | -------------- | ---------------------------------------------------------------------------------- |
   | -A             | The same results as -vET.                                                          |
   | -v             | Prints strings that are not originally printed separately in the form of ^ and M-. |
   | -E             | Prints $ at the end of each line.                                                  |
   | -T             | Prints TAB in the form of ^l.                                                      |

{{< vs 2 >}}

---
## Examples

   - *cat*
  
      {{< img src="images/cat.png" >}}

   {{< vs 2>}}
   - *cat -A*

     {{< img src="images/cata.png" >}}
