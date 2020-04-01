# jefferson
JFFS2 filesystem extraction tool

## Branches
- version-fix : this version should work with Binwalk using python 3.
- master : this is the old code that is python 2 and was giving me fits when used with Binwalk and python 3.

Installation
============
```bash
$ sudo python setup.py install
```


Dependencies
============
- `cstruct`
- `pyliblzma`

```bash
$ sudo pip install cstruct
$ sudo apt-get install python-lzma
```

Features
============
- Big/Little Endian support
- `JFFS2_COMPR_ZLIB`, `JFFS2_COMPR_RTIME`, and `JFFS2_COMPR_LZMA` compression support
- CRC checks - for now only enforced on `hdr_crc`
- Extraction of symlinks, directories, files, and device nodes
- Detection/handling of duplicate inode numbers. Occurs if multiple JFFS2 filesystems are found in one file and causes `jefferson` to treat segments as separate filesystems

Usage
============
```bash
$ jefferson filesystem.img -d outdir
```
