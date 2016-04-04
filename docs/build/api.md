
Note that nothing in this package is exported.


<a id='Index-1'></a>

## Index

- [`CHM.CHMFile`](api.md#CHM.CHMFile)
- [`CHM.CHMUnitInfo`](api.md#CHM.CHMUnitInfo)
- [`CHM.close`](api.md#CHM.close)
- [`CHM.open`](api.md#CHM.open)
- [`CHM.readdir`](api.md#CHM.readdir)
- [`CHM.resolve`](api.md#CHM.resolve)
- [`CHM.retrieve`](api.md#CHM.retrieve)
- [`CHM.unitinfo`](api.md#CHM.unitinfo)

<a id='Types-1'></a>

## Types

<a id='CHM.CHMFile' href='#CHM.CHMFile'>#</a>
**`CHM.CHMFile`** &mdash; *Type*.

---


Custom type for dispatching only. Not needed by user.

<a id='CHM.CHMUnitInfo' href='#CHM.CHMUnitInfo'>#</a>
**`CHM.CHMUnitInfo`** &mdash; *Type*.

---


"Julia type wrapper for a C struct from CHMLib that contains information on\nmetadata for an object within the .chm file.\n"

<a id='Functions-1'></a>

## Functions

<a id='CHM.close' href='#CHM.close'>#</a>
**`CHM.close`** &mdash; *Function*.

---


`close(ptr::Ptr{CHMFile})`

Close a file with CHMLib.

<a id='CHM.open' href='#CHM.open'>#</a>
**`CHM.open`** &mdash; *Function*.

---


`open(path::ASCIIString)`

Open a file with CHMLib.

<a id='CHM.readdir' href='#CHM.readdir'>#</a>
**`CHM.readdir`** &mdash; *Function*.

---


`readdir(ptr::Ptr{CHMFile}, path::ASCIIString)`

Read the contents of a given directory in the CHM file. Use UNIX path conventions. Root level is "/". Returns the file and directory names.

<a id='CHM.resolve' href='#CHM.resolve'>#</a>
**`CHM.resolve`** &mdash; *Function*.

---


`resolve(ptr::Ptr{CHMFile}, path::ASCIIString)`

Returns `true` if `path` in the .chm file resolves to a file, else `false`.

<a id='CHM.retrieve' href='#CHM.retrieve'>#</a>
**`CHM.retrieve`** &mdash; *Function*.

---


`retrieve(ptr::Ptr{CHMFile}, path::ASCIIString)`

Returns a string containing the contents of a text file at `path` within the .chm file.

<a id='CHM.unitinfo' href='#CHM.unitinfo'>#</a>
**`CHM.unitinfo`** &mdash; *Function*.

---


`unitinfo(ptr::Ptr{CHMFile}, path::ASCIIString)`

Returns a `CHMUnitInfo` object for the file at `path` within the .chm file.

