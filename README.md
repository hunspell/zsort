# About zsort

zsort is a Hungarian sorting script written in awk, also a
demonstration of Hunspell morphological analysis.

Hungarian digraphs cs, dz, gy, ly, ny, sz, ty, and zs, also
trigraph dzs, moreover their simplified double forms
ccs, ddz, ggy, lly, nny, ssz, tty, zzs and ddzs result frequent
ambiguity in Hungarian word collating, sorting and hyphenation.
Recent collate algorithms of glibc locale and ICU/Unicode CLDR cannot
handle this ambiguity, resulting bad Hungarian collation and sorting.

zsort is a free command-line equivalent of the web tool akhsort
(that developed by Research Institute for Linguistics of
Hungarian Academy of Sciences). But unlike akhsort, zsort works
with compound words and titles correctly, and it has no limitations
(for example, it can sort millions of words within a few minutes) and
known dictionary bugs (like bad sorting of “másszor” in akhsort).

# Installation

zsort needs not only Hunspell, but a recent Hungarian Hunspell
dictionary, too. That will be available in LibreOffice repository:

```
wget https://github.com/LibreOffice/dictionaries/blob/master/hu_HU/hu_HU.aff?raw=true -O hu_HU.aff
wget https://github.com/LibreOffice/dictionaries/blob/master/hu_HU/hu_HU.dic?raw=true -O hu_HU.dic
sudo cp hu_HU.aff hu_HU.dic /usr/share/hunspell
```

# Usage

```
cat text | zsort
```

# Unit testing

Check hunspell and its Hungarian dictionary (Magyar Ispell 1.7 or newer):

```
zsort -v check=1
```

# More

See it in the command-line script.
