# zip

Ext adapters for package managers, runtimes and toolchains.

| Group | Adapters |
| --- | --- |
| Package and version managers | `homebrew`, `nvm` |
| Language runtimes | `node`, `python`, `jvm`, `php` |
| Toolchains and SDKs | `git`, `xcode` |
| Evaluators | `wasm`, `evm` |

## Relationship to ext

These are [ext](https://github.com/webong/ext) packages. Each directory is one
adapter with its own `ext.json` manifest; ext installs, trusts and invokes it
through the plugin contract. Nothing here is built into ext itself. See ext's
[adapter authoring](https://github.com/webong/ext/blob/main/docs/adapter-authoring.md)
and [package sources](https://github.com/webong/ext/blob/main/docs/source-management.md)
guides.

The history of each adapter was carried over from `webong/ext` when the
adapters moved out of that repository. References like `webong/ext#123` in
older commit messages point at ext's pull requests.

## Development

`go.work` at the root ties the Go modules together:

- Modules here are not tagged; `go.work` resolves them from the tree.
- ext has not tagged several modules these adapters need, so `go.work` pins
  every ext module to one ext commit. Delete that block once ext tags releases.

```sh
go vet ./<adapter>/...
go test ./<adapter>/...
```
