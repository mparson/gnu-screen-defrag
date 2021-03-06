# GNU screen defrag

After opening and closing various windows inside of [GNU screen](https://www.gnu.org/software/screen/), you wind up with holes in your window list:

```
 Num Name                                                                  Flags
 
   0 irc
   1 proclog                                                                    
   2 weblog
   3 alpine
   5 bash
   6 test stuff
   7 bash
   8 bash
  10 maillog
```

This means that the next window opened will be at the next available number, which in this case, would be '4', the next one would be '9'.

This script, when executed, will re-number all of your windows, starting with '0' so that there are no more holes in your window numbers:

```
 Num Name                                                                  Flags
 
   0 irc
   1 proclog                                                                    
   2 weblog
   3 alpine
   4 bash
   5 test stuff
   6 bash
   7 bash
   8 maillog
```

Now, my next new window will be opened at the end of the list, starting with '9', then '10', etc.

To make it easier, I bind it to a key in my `.screenrc` as such:

```
...
bind R /home/mparson/bin/scdefrag
...
```

I can then just hit `CTRL-A` `R` and my windows get re-numbered.

---
This requires a feature introduced in GNU screen 4.0.3.  For older versions of screen, check out the original commit to this project.