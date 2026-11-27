# Third-party notice: go-ethereum

The `ctx-evm` executable in this package links the **go-ethereum** library,
`github.com/ethereum/go-ethereum` (version recorded in `go.mod`), for its EVM
interpreter. go-ethereum's library code is licensed under the **GNU Lesser
General Public License v3.0**. The license texts are in
[`third_party/go-ethereum/COPYING.LESSER`](third_party/go-ethereum/COPYING.LESSER)
and [`third_party/go-ethereum/COPYING`](third_party/go-ethereum/COPYING).

- **Source of go-ethereum:** <https://github.com/ethereum/go-ethereum>, at the version in
  this package's `go.mod`.
- **Source of this adapter:** the `evm` directory of
  <https://github.com/xallet/zip>, which also builds the executable. Its history before
  the move is in the `adapters/evm` directory of <https://github.com/webong/ext>.
- **Your rights under the LGPL:** you may replace go-ethereum with a modified version and
  rebuild `ctx-evm` from the adapter source. For example, add
  `replace github.com/ethereum/go-ethereum => /path/to/your/go-ethereum` to `go.mod` and run
  `ctx adapter build ./evm` from a checkout of xallet/zip, then reinstall the package.

ext (`ctx`, `ctn` and the libraries) does not link go-ethereum. The dependency
is confined to this one adapter executable, so the license of the adapter's third-party code
does not extend to the other ext binaries or libraries.
