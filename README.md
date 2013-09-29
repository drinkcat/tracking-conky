tracking-conky
==============

Package tracking for conky (or any other application where you'd like to have a text-only tracking information). Only supports DHL tracking at this stage.

Some more details on [my blog](http://drinkcat.blogspot.com/2013/09/tracking-your-dhl-package-in-conky.html).

Usage
-----

```
./dhl <AWB>
```

Where `<AWB>` is the Waybill number (tracking number). It produces a text-only tracking information for your package.

You can integrate it in your conky with something like:

```
${font Monospace:size=6}${execi 60 ~/.conky/dhl <AWB> | head -n 3 | fold -w 16}$font
```

Replace `~/.conky/dhl` with the path to where you copied the script. Change `head` parameter if you want more lines, and `fold` inserts new lines every 16 characters (change that depending on your conky width).
