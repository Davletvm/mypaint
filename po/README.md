## New translation

To start a new language, generate only the template mypaint.pot with:

```
scons translate=pot
```

Then put a new .po file into this directory. To make such a file you can copy 
the header from an existing .po file and modify accordingly.

Unless there are several country specific dialects for your language the file
should be named ll.po where "ll" is your language code given by [1]

If there are several dialects, the file should be named `ll_CC.po` where
"CC" is your country code given by [2]

## Update translation

Before working on a translation, update the po file for your language.
For example, for the French translation, run:

```
scons translate=fr
```

## Use/Test the translation

After modifying the translation you need to rebuild to see the changes:

```
scons
```

To run MyPaint with a specific translation on Linux you can use the 
LANG environment variable like this (the locale needs to be supported):

```
LANG=ll_CC.utf8 ./mypaint
```

where "ll" and "CC" are language/country codes given by [1] and [2] respectivly
and your working directory is the root directory of mypaint 

To run MyPaint with the original strings, for comparison, you can use
the `LC_MESSAGES` variable like this:

```
LC_MESSAGES=C ./mypaint
```

## Send changes

Before you send your changes, please make sure that your changes are based 
on the current development (git) version of MyPaint.

We prefer changes as Github pull requests, but if you do not know git just
send a unified diff or the updated .po file along with your name to:
a.t.chadwick (AT) gmail.com

If you are interested in keeping the transalation up to date, please subscribe to
mypaint-discuss (AT) gna.org


## References

Official GNU gettext manual
http://www.gnu.org/software/hello/manual/gettext/
1. "ll" options: http://www.gnu.org/software/hello/manual/gettext/Usual-Language-Codes.html#Usual-Language-Codes
2. "CC" options: http://www.gnu.org/software/hello/manual/gettext/Country-Codes.html#Country-Codes
