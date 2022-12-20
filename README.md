# gh-get-asset

Fetch an asset from a release

## Installation

```shell
gh extension install chmouel/gh-get-asset
```

### Requirements

- [GH](https://github.com/cli/cli)
- [JQ](https://stedolan.github.io/jq/)

## Usage

gh get-asset extension let you download an asset (ie: binary or others) from a release page.

by default the first argument is the `owner/repo` and second argument is a substring in the asset.

example:

```console
gh get-asset chmouel/gosmee Linux-ARM64.rpm
```

this will grab the latest release from
[gosmee](https://github.com/chmouel/gosmee) that has Linux-ARM64.rpm in the
binary name.

If you want to output it to another file or location you can use `-o` :

```console
gh get-asset -o/tmp/gosmee.rpm chmouel/gosmee Linux-ARM64.rpm && rpm -Uvh /tmp/gosmee.rpm
```

If you have multiple binary matching it will get all of them (incompatible
with -o option)

You can add `-s` for silent te output of curl (useful for crons)

By default it will always grab the latest release unless you specify `-r
RELEASE` to grab another release.

## Copyright

[Apache-2.0](./LICENSE)

## TODO

- Use gh token to grab releases/asset for private repos.

## Authors

Chmouel Boudjnah

- Fediverse - <[@chmouel@fosstodon.org](https://fosstodon.org/@chmouel)>
- Twitter - <[@chmouel](https://twitter.com/chmouel)>
- Blog  - <[https://blog.chmouel.com](https://blog.chmouel.com)>
