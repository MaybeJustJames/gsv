# gsv

[![Package Version](https://img.shields.io/hexpm/v/gsv)](https://hex.pm/packages/gsv)
[![Hex Docs](https://img.shields.io/badge/hex-docs-ffaff3)](https://hexdocs.pm/gsv/)

This is a simple csv parser and writer for gleam. It will get more performant in the future,
but if you're looking for high performance now, I'd recommend doing ffi to an existing parser
in your target runtime.

We are using the grammar from [rfc 4180](https://datatracker.ietf.org/doc/html/rfc4180#section-2)

#### Example

```gleam
import gsv.{Unix, Windows}

pub fn main() {
  let csv_str = "Hello, World\nGoodbye, Mars"

  // Parse a CSV string to a List(List(String))
  let assert Ok(records) = gsv.to_lists(csv_str)

  // Write a List(List(String)) to a CSV string
  let csv_str = records
  |> gsv.from_lists(separator: ",", line_ending: Windows)
}
```

## Installation

If available on Hex this package can be added to your Gleam project:

```sh
gleam add gsv
```

and its documentation can be found at <https://hexdocs.pm/gsv>.
