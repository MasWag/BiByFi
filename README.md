# BiByFi
 *This project has been under developing. The API may be broken dramatically and suddenly*

A bibliography framework for [SATySFi](https://github.com/gfngfn/SATySFi)

This project is inspired by [cs-thesis](https://github.com/gfngfn/cs-thesis) and borrowing many codes from [it](https://github.com/gfngfn/cs-thesis).

# Usage
See the `example` directory for complete documents.

## Rendering one bibliography entry

Require the core package and the APA renderer:

```saty
@require: bibyfi/bibyfi
@require: bibyfi/bibyfi-APA
```

`+bibentry` accepts a renderer and a `bibyfi-item` directly, so it can be
placed anywhere a block command is accepted:

```saty
+section{Robust Semantics}<
  +bibentry(BiByFiAPA.render BiByFiAPA.default-config)(
    Article((|
      author = [`Donzé, A.`; `Maler, O.`];
      title = `Robust satisfaction of temporal logic over real-valued signals`;
      journal = `Formal Modeling and Analysis of Timed Systems`;
      year = `2010`;
      pages = (`92`, `106`);
      volume = None;
      number = None;
      month = None;
      note = Some(`doi:10.1007/978-3-642-15297-9_9`);
      key = None;
    |))
  );
  ...
>
```

This command does not register a citation, access citation logs, require a
label, or require a global bibliography.

The APA renderer supports `Article`, `Book`, `InProceedings`, `TechReport`,
`Misc`, and `WildCard`. Other constructors produce an unsupported-item
message. Author names must already be APA-ready, for example `Donzé, A.`.
The existing BiByFi records have no dedicated DOI or URL field; put such text
in `note`, or in `howpublished` for `Misc`.

# Install
```sh
opam install satysfi-bibyfi
```

![screenshot](https://raw.githubusercontent.com/namachan10777/bibyfi/master/screenshot.png)
