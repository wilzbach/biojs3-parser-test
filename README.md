In development: BioJS parsers with web components
=================================================

Have a look at https://github.com/biojs/biojs3 for more info.


Simple parsers
--------------

Parsers should work by 

### using the `url` attribute

```
<biojs-vis-msa>
    <biojs-io-fasta url="./foo.fasta" />
</biojs-vis-msa>
```

Note: __custom elements__ always need to be closed.
However once the parent gets closed, they will be closed too.

### using `textContent`

```
<biojs-vis-msa>
    <biojs-io-fasta data={{seqs}}>
    some inner text
    </biojs-io-fasta>
</biojs-vis-msa>
```

Data binding between components
-------------------------------

### Putting the parser as child of one visualization

```
<template is="dom-bind">
    <biojs-vis-msa id="msa1" seqs="{{seqs}}">
        <biojs-io-fasta url="./foo.fasta" />
    </biojs-vis-msa>

    <biojs-vis-msa id="msa2" seqs="{{seqs}}"></biojs-vis-msa>
</template>
```

### Having the parser on the same level

```
<template is="dom-bind">

    <biojs-vis-msa id="msa1" seqs="{{seqs}}"></biojs-vis-msa>
    <biojs-vis-msa id="msa2" seqs="{{seqs}}"></biojs-vis-msa>

    <biojs-io-fasta url="./foo.fasta" data="{{seqs}}"/>
</template>
```
