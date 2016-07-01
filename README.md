# cmslib-exec
Libraries and executables for CMS to run cross compiled code.

`zlib.txtlib` contains unmodified `zlib-1.2.8`.

All files except the pdf and tar should be uploaded binary fixed 80.

Libraries should be used as is.
The VM archive contains EXECs.

Documentation is `gcc390.pdf`.

The source for these files are in a separate project,
`cmslib`.
You also need to install the utilities in `gas2asm`.

ZLIBSTG filter package
----------------------

The vm archive contains _inter alia_ the filter package `ZLIBSTG MODULE`.

```
ZLIB COMPRESS|DEFLATE [<number>]
```
The number specifies the compression level from 0 (no compression) to 9,
which is the most aggressive.  A number that is not 0..9 is treated as
`Z_DEFAULT_COMPRESSION`.
```
ZLIB EXPAND|INFLATE
```
__Note:__ both filters
operate on a byte stream; you will likely perform some kind
of blocking to retain record boundaries.  Adding a line end character is
likely to lead to most efficient compression, but `ADDRDW SF4` is the most
general.

Change activity
---------------

2016-06-30  Add `zlib` and a filter package for _CMS/TSO Pipelines_
            that contains `zlib compress` and `zlib expand` filters.

2016-07-01  Support on `ZLIB COMPRESS` a number to specify the compression
            level.
