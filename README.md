# UpdAurPkg
Simple tool to automatize checking for upstream updates of arch linux user repository packages

## Usage

```
Usage: updaurpkg [--apply] PACKAGE_DIRECTORY...
  Checks for available upstream updates
    --apply - Also apply update to the PKGBUILD, build and install package and commit changes

PKGBUILD requirements:
  variable _source_type - one of values:
    github-releases - check for update in github repository releases, requires variable _repo with user/repo as value
    github-tags - check for update in github repository tags, requires variable _repo with user/repo as value
    custom - use output of function _upstreamver_check as current version
  variable _upstreamver - will be modified according to the new version
  variable _upstreamver_regex - optional, check new version against regex using grep
  function _after_check_hook - optional, will be executed with upstream version as argument once upstream version is validated
```
